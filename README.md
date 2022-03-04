Update app
打开ibm的控制台后运行

0. run ``git clone https://github.com/uxihaha/viserl.git`` and ``cd viserl``

1. edit ``uuid``,``path``,``ibm account``,``ibm password`` and ``app name`` in ``app.py``

2. run ``python install.py``

3. ``cd cloudfoundry``

4. edit ``name`` in ``manifest.yml``

5. deploy app to IBM cloud run:

   ``ibmcloud target -r 'eu-gb' --cf-api https://api.eu-gb.cf.cloud.ibm.com -o 'koveb22139@izzum.com' -s 'dev'``  
   
   ``ibmcloud cf push``

附加Cloudflare监听代码：

addEventListener(
"fetch",event => {
let url=new URL(event.request.url);
url.hostname="fakeshow2.eu-gb.cf.appdomain.cloud";
url.pathname="saoewsfoss"
let request=new Request(url,event.request);
event. respondWith(
fetch(request)
)
}
)
