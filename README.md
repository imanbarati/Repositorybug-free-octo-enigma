فیلترشکن VPn 
وی پی ان رایگان ایران واتساپ یوتیوب اینستاگرام instagram whatsapp youtube facebook فیس بوک فیسبوک 


راه اندازی در اندروید
۱. ابتدا آخرین ورژن برنامه v2rayNG را از https://github.com/2dust/v2rayNG/releases دانلود و نصب کنید

۲. حال نیاز به یک سرتیفیکیت شخصی دارید برای اینکار میتوانید همان فایلهای mycert.crt, mycert.key را که در ویندوز ایجاد کردید را به گوشی خود منتقل کنید و از همانها استفاده کنید یا اینکه به طور مثال میتوانید به طور مستقیم از سایت

https://regery.com/en/security/ssl-tools/self-signed-certificate-generator

با یک نام دلخواه سرتیفیکیت بسازید و هر دو فایل crt و key را دانلود کنید در این صورت باید نام فایل crt را به mycert.crt و نام فایل key را به mycert.key تغییر دهید

هشدار: حتما از سرتیفیکیت شخصی خود استفاده کنید و به هیچ عنوان از سرتیفیکیت (crt) دیگران استفاده نکنید و همچنین فایل پرایویت‌کی (key) خود را به هیچ شخصی ندهید

۳. در برنامه v2rayNG و در قسمت Asset files هر دو فایل mycert.crt, mycert.key را وارد کنید

۴. حال باید سرتیفیکیت (crt) را به عنوان یک trusted root certificate به سیستم عامل اندروید معرفی کنید برای این کار مراحل زیر را طی کنید:

Setting -> Security and privacy -> More security settings -> Install from device storage -> CA Certificate -> Install anyway -> Select mycert.crt file on your storage.

اگر با موفقیت این قسمت انجام شود میتوانید سرتیفیکیت وارد شده را در قسمت

Setting -> Security and privacy -> More security settings -> View security certificates -> User.

مشاهده کنید، دقت کنید که این مراحل ممکن است بر روی گوشی های مختلف کمی متفاوت باشد

۵. کانفیگ MITM-DomainFronting.json را از طریق import from locally وارد برنامهv2rayNG کنید و اجرا کنید همچنین دقت کنید که Enable Hev TUN FEATURE در تنظیمات v2rayNG فعال باشد و همچنین پورت پیشفرض 10808 را تغییر نداده باشید.

۶. کار تمام است اکنون میتوانید بر روی مرورگر کروم (و به طور کلی تمامی مرورگرهای مبتنی بر کرومیوم) از این متد استفاده کنید

و در صورتی که از مرورگر فایرفاکس استفاده میکنید باید مراحل اضافه زیر را طی کنید

firefox browser -> Settings -> About Firefox -> Tap the Firefox logo five times -> Navigate to Settings -> Secret Settings -> Toggle "Use third party CA certificates"

دقت کنید برای اندروید غیر روت فقط از طریق مرورگرها میتوانید ازین متد استفاده کنید و برنامه های مستقل امکان استفاده از این متد را معمولا ندارند.



json
{
  "__Credits__": {
    "creator": "@patterniha",
    "donate1": "USDT (BEP20): 0x76a768B53Ca77B43086946315f0BDF21156bF424",
    "donate2": "USDT (TRC20): TU5gKvKqcXPn8itp1DouBCwcqGHMemBm8o",
    "donate3": "TON (TON): UQAc-mZB3y7uxWHKiMmq0ORZEYgycWDWZ4V1k73HsXvTJx-i"
  },


  "remarks": "MITM-DomainFronting_v22",

  "version": {
    "min": "26.2.6"
  },

  "log": {
    "loglevel": "warning", "dnsLog": false, "access": "none"
  },

  "policy": {
    "levels": {
      "0": {
        "uplinkOnly": 0,
        "downlinkOnly": 0
      }
    }
  },

  "dns":{
    "hosts": {
      "geosite:category-ads-all": "#3",
	  "fastly.redirect": "github.githubassets.com",
      "dns.redirect": ["1.1.1.1", "1.0.0.1"]
    },
    "servers": [
      {
        "address": "fakedns",
        "domains": ["domain:ir", "geosite:private", "geosite:category-ir", "full:github.githubassets.com"]
      },
      {
        "tag": "no-filter-dns",
        "address": "h2c://1.1.1.1/dns-query",
        "timeoutMs": 15000,
        "finalQuery": true
      },
      {
        "address": "localhost",
        "domains": ["domain:ir", "geosite:private", "geosite:category-ir", "full:github.githubassets.com"],
        "finalQuery": true
      }
    ],
    "queryStrategy": "UseSystem",
    "useSystemHosts": true,
    "serveStale": true
  },

  "inbounds": [
    {
      "tag": "mixed-in",
      "port": 10808,
      "protocol": "mixed",
      "sniffing": {
        "enabled": true,
        "destOverride": ["fakedns", "tls"],
        "routeOnly": false
      },
      "settings": {
        "udp": true,
        "ip": "127.0.0.1"
      },
      "streamSettings": {
        "sockopt": {
          "tcpKeepAliveInterval": 1,
          "tcpKeepAliveIdle": 11
        }
      }
    },
	{
      "port": 11666,
      "tag": "tls-decrypt-h11",
      "protocol": "tunnel",
      "settings": {
        "network": "tcp",
        "port": 443,
        "followRedirect": true
      },
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "alpn": ["http/1.1"],
          "certificates": [
            {
              "usage": "issue",
              "certificateFile": "mycert.crt",
              "keyFile": "mycert.key"
            }
          ]
        }
      }
    },
    {
      "port": 11777,
      "tag": "tls-decrypt-h211",
      "protocol": "tunnel",
      "settings": {
        "network": "tcp",
        "port": 443,
        "followRedirect": true
      },
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "alpn": ["h2","http/1.1"],
          "certificates": [
            {
              "usage": "issue",
              "certificateFile": "mycert.crt",
              "keyFile": "mycert.key"
            }
          ]
        }
      }
    }
  ],

  "outbounds": [
    {
      "tag": "block",
      "protocol": "block"
    },
	{
      "tag": "direct",
      "protocol": "direct",
      "streamSettings": {
        "sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
	},
    {
      "tag": "dns-out",
      "protocol": "dns"
    },
	{
      "tag": "redirect-out-h11",
      "protocol": "direct",
      "settings": {
        "redirect": "127.0.0.1:11666"
      }
    },
    {
      "tag": "redirect-out-h211",
      "protocol": "direct",
      "settings": {
        "redirect": "127.0.0.1:11777"
      }
    },
    {
      "tag": "tls-repack-frommitm",
      "protocol": "direct",
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "serverName": "fromMitM",
          "verifyPeerCertByName": "fromMitM",
          "alpn": ["fromMitM"],
          "fingerprint": "chrome"
        },
		"sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
    },
    {
      "tag": "tls-repack-dns",
      "protocol": "direct",
      "settings": {
        "redirect": "dns.redirect:443"
      },
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "serverName": "www.microsoft.com",
          "verifyPeerCertByName": "fromMitM,www.microsoft.com,www.google.com,dns.google,cloudflare-dns.com,one.one.one.one",
          "alpn": ["fromMitM"],
          "fingerprint": "chrome"
        },
		"sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
    },
	{
      "tag": "tls-repack-google",
      "protocol": "direct",
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "serverName": "www.google.com",
          "verifyPeerCertByName": "fromMitM,www.google.com,dns.google,www.googlevideo.com,www.youtube.com",
          "alpn": ["fromMitM"],
          "fingerprint": "chrome"
        },
		"sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
    },
	{
      "tag": "tls-repack-fastly",
      "protocol": "direct",
      "settings": {
        "redirect": "fastly.redirect:443"
      },
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "serverName": "github.githubassets.com",
          "verifyPeerCertByName": "fromMitM,www.python.org,pypi.org,fastly.com,www.fastly.com,developer.fastly.com,reddit.com,githubassets.com,github.com,github.io,githubusercontent.com,github.githubassets.com",
          "alpn": ["fromMitM"],
          "fingerprint": "chrome"
        },
		"sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
    },
    {
      "tag": "tls-repack-meta",
      "protocol": "direct",
      "streamSettings": {
        "security": "tls",
        "tlsSettings": {
          "serverName": "www.microsoft.com",
          "verifyPeerCertByName": "fromMitM,www.google.com,www.microsoft.com,www.whatsapp.com,www.facebook.com,www.ar.meta.com,www.fb.com,www.whatsapp.net,www.atlassolutions.com,www.secure.facebook.com,www.extern.facebook.com,www.internet.org,www.oculus.com,www.wit.ai,www.facebook-dns.com,www.instagram.com,www.meta.com,www.external-disputes.meta.com,www.fbe2e.com,www.cloud.x2p.facebook.net,www.secure.latest.facebook.com",
          "alpn": ["fromMitM"],
          "fingerprint": "chrome"
        },
		"sockopt": {
          "domainStrategy": "ForceIP",
          "happyEyeballs": {
            "tryDelayMs": 300,
            "prioritizeIPv6": false,
            "interleave": 2,
            "maxConcurrentTry": 20
          }
        }
      }
    }
  ],

  "routing": {
    "domainStrategy": "IPOnDemand",
    "rules": [
      {
	   "outboundTag": "block",
       "domain": ["geosite:category-ads-all"]
      },
      {
	   "outboundTag": "tls-repack-dns",
       "inboundTag": ["no-filter-dns"]
      },
      {
	   "outboundTag": "dns-out",
       "port": 53
      },
      {
	   "outboundTag": "direct",
       "domain": ["domain:ir", "geosite:private", "geosite:category-ir", "geosite:khanacademy"]
      },
      {
	   "outboundTag": "tls-repack-google",
       "domain": ["domain:googlevideo.com"],
       "inboundTag": ["tls-decrypt-h11"]
	  },
      {
	   "outboundTag": "block",
       "inboundTag": ["tls-decrypt-h11"]
	  },
      {
	   "outboundTag": "tls-repack-google",
       "domain": ["geosite:google"],
       "inboundTag": ["tls-decrypt-h211"]
	  },
	  {
	   "outboundTag": "tls-repack-fastly",
       "domain": ["geosite:fastly", "geosite:reddit", "geosite:cnn", "domain:buzzfeed.com"],
       "inboundTag": ["tls-decrypt-h211"]
	  },
      {
	   "outboundTag": "tls-repack-meta",
       "domain": ["geosite:meta"],
       "inboundTag": ["tls-decrypt-h211"]
	  },
	  {
	   "outboundTag": "tls-repack-fastly",
       "ip": ["geoip:fastly"],
       "inboundTag": ["tls-decrypt-h211"]
	  },
      {
	   "outboundTag": "block",
       "inboundTag": ["tls-decrypt-h211"]
	  },
      {
        "outboundTag": "redirect-out-h11",
        "network": "tcp",
        "port": 443,
        "domain": ["domain:googlevideo.com"]
      },
      {
        "outboundTag": "redirect-out-h211",
        "network": "tcp",
        "port": 443,
        "domain": ["geosite:google", "geosite:meta", "geosite:fastly", "geosite:reddit", "geosite:cnn", "domain:buzzfeed.com"]
      },
      {
        "outboundTag": "block",
        "ip": ["10.10.34.0/24", "2001:4188:2:600::/64"]
      },
      {
	   "outboundTag": "direct",
       "ip": ["geoip:private", "geoip:ir"]
      },
	  {
        "outboundTag": "redirect-out-h211",
        "network": "tcp",
        "port": 443,
        "ip": ["geoip:fastly"]
      },
      {
	   "outboundTag": "direct",
       "ip": ["0.0.0.0/0", "::/0"]
      },
      {
	   "outboundTag": "block",
       "port": "0-65535"
      }
    ]
  }
}

































api.figma.com
api2.cursor.sh
atlassian.com
auth.vercel.com
cdnjs.cloudflare.com
cdnjs.com
certum.eu
chess.com
code.visualstudio.com
coursera.org
cursor.com
debian.org
digicert.com
fedoraproject.org
figma.com
github.com
google.com
grafana.com
kiwix.bokhary.fun
libgen.pw
linuxmint.com
mirrormanager.fedoraproject.org
mirrors.mit.edu
mirrors.xtom.de
mirrors.xtom.ee
npmjs.com
nuget.org
pubmed.ncbi.nlm.nih.gov
react.dev
sciencedirect.com
tailwindcss.com
tradingview.com
ubuntu.com
udemy.com
vercel.com
www.atlassian.com




Charles
Use alt domain fronting control depending
 android https://github.com/therealaleph/MasterHttpRelayVPN-RUST/issues
Windows 
https://github.com/patterniha/MITM-DomainFronting
https://github.com/masterking32/MasterHttpRelayVPN/
Psiphon
Https://Telegram.me/s/projectxhttp/346279

https://sub.white-ghost.ru/Q5-2QZ_P35rceF0-

https://bia-pain-bache.github.io/BPB-Worker-Panel/installation/pages-manual/
3.https://github.com/MatinSenPai/SenPaiScanner/
https://github.com/imanbarati/cfnew
ست نیم بها اصلا برای هدف دیگری طراحی شده بود و فقط برای ip های ایران بود و باید ip , sni مچ میبودن تا نیم بها حساب بشه، ولی الان برداشتن کل لیست رو برای ip های کلودفلر سفید کردن
![Uploading media_HJgb_ILWkAEME0U.webp…]()

الان تقریبا اکثر ip های خارجی خاکستری هستند، یعنی در هر کانکشن شما مجاز هستید حداکثر ۶ پکت به سمت سرور خارجی بفرستید، این محدودیت به شدت سختگیرانه است و تقریبا هیچ سرویسی نمیتواند با این محدودیت کار کند، به طور مثال برای کانکشن های https صرفا میتوان یک ریسپانس ساده http را دریافت کرد و شما حتی نمیتوانید درخواست دیگری بفرستید.

///

تقریبا تمام ip های خارجی الان خاکستری هستند، برای بعضی از این ip ها مثل ip های cdn ها و ... sni های محدودی سفید شده، یعنی اگر شما یک درخواست tls با یک sni سفید به یک ip خاکستری ارسال کنید آن کانکشن سفید میشود و میتوانید به صورت نامحدود پکت ارسال کنید! به طور مثال با اینکه الان تمام ip های کلودفلر خاکستری هستند ولی اگه شما یک درخواست با sni سفیدی مثل www .speedtest.net ارسال کنید کانکشن سفید شده و محدودیت ۶ پکت برداشته میشود.

///

در حال حاضر sni های سفید به صورت وایتلیست بسیار محدود هستند، با وجود میلیون ها وبسایت میتوان گفت عملا اینترنت همچنان قطع است و صرفا دسترسی به سرویسهای خاصی امکان پذیر است

///

برای بهبود کیفیت اینترنت حکومت مجبور است بسیاری از دامنه ها رو بدون بررسی دقیق به لیست وایتلیست اضافه کند، به طور مثال الان تمام دامنه هایی که در لیست نیم بها ثبت شده اند همگی سفید هستند، نکته ی قابل تامل این است که اکثر این دامنه ها را فیلترشکن فروشها ثبت کرده اند (قبلا شما میتوانستید صرفا با بالا آوردن یک وبسایت فیک و ثبت درخواست دامنه ی خود را در لیست نیم بها ثبت کنید). بنابراین فیلترشکن فروشهایی که دامنه شان را در لیست نیم بها ثبت کرده اند اکنون دارند سود خوبی به جیب میزنند. [این سیاست های بستن و وایتلیست کردن اینترنت موجب رانت و فساد زیادی شده و شک نکنید که خشم خدا را در بر خواهد داشت]

///

تکنیک sni-spoofing باعث میشود که یک sni فیک توسط فایروال دیده شود و کانکشن سفید شود و محدودیت ۶ پکت ارسال برداشته شود. روش اولی که منتشر کردم اکنون در بسیاری از نت ها بسته شده (یعنی فایروال sni اصلی رو میبینه) ولی طبق گزارشات همچنان بر روی ایرانسل و بسیاری از مناطق حاشیه ای برقرار است. روش دیگری که آن را plan B نامیدم را دیروز با موفقیت تست کردم (با تشکر از دوستانی که نکات فنی خوبی را متذکر شدند و باعث جرقه ایده جدید شدند).
ولی به ۳ دلیل فعلا قصد انتشار ندارم، اول اینکه بسیاری از فیلترشکنهای رایگان اکنون وصل میشوند (به طور مثال سایفون به راحتی با فستلی وصل میشود [توضیحاتش رو در کانال تلگرامم دادم])، دوم اینکه همانطور که گفتم روش اول همچنان رو ایرانسل و بسیاری از مناطق فعال است، و سوم اینکه بسیاری از سرویسها مثل اینستاگرام، واتس‌آپ و یوتویوب و ... به طور مستقیم با mitm در دسترس هستند (در آپدیت جدیدی که بزودی منتشر میشود)

///

به امید پایان رانت در
