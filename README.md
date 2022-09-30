# python-django
 Django-Tutorial — the tutorial for DjangoPython
 
ภาษา Python เริ่มถูกใช้งานอย่างแพร่หลายมากขึ้นเรื่อยๆ ในช่วงนี้เนื่องจากความง่ายในการเรียนรู้ และความสะดวกในการทดสอบโปรแกรม เนื่องจาก Python เป็นภาษาประเภท Script ซึ่งจะแตกต่างกับภาษาประเภท Java หรือ C ที่ต้อง compile code ให้ออกมาเป็น binary ก่อนนำไปรันได้จริง เช่น หากต้องการทดสอบ function substring ว่าจะสามารถตัดคำให้เราถูกต้องหรือไม่ กรณีใช้ภาษา Java หรือ C ก็ต้องเขียน class, main function หรืออื่นๆ อีกมากมายกว่าจะเริ่มทดสอบ function เล็กๆ นี้ได้ แต่ใน Python นั้น เพียงแค่เข้า Python console ก็สามารถทดสอบ function เหล่านี้ได้ทันที

Django (อ่านว่าจังโก้ หรือแจงโก้ โดยไม่ออกเสียงตัว D) เป็น framework ที่ใช้ในการสร้าง Web Application ในฝั่งของ Back End ที่พัฒนาด้วยภาษา Python โดยในตัว framework จะมีส่วนประกอบทุกอย่างที่จำเป็นตั้งแต่การเชื่อมต่อฐานข้อมูล ไปจนถึงการ render ข้อมูลออกมาให้ฝั่ง Front End แสดงผลข้อมูลเหล่านั้นได้ ซึ่ง framework ในรูปแบบนี้ในภาษาอื่นๆ เช่น Ruby on rails สำหรับภาษา Ruby, Play Framework สำหรับภาษา Java หรือ Scala, Groovy on Grails สำหรับภาษา Groovy, Laravel สำหรับภาษา PHP, หรือ Express สำหรับภาษา Javascript ของ Node.js เป็นต้น ซึ่งข้อมูลที่อ้างอิงมาจาก www.hotframeworks.com จะเห็นว่า Django มีการใช้งานอย่างแพร่หลายมาก

การติดตั้ง Python และ Django
ติดตั้ง Python
- สำหรับ Windows สามารถ Download ได้จาก ที่นี่ ** สำคัญมากต้องติ๊กช่อง “Add python 3.X to PATH” ด้วย
- สำหรับ Linux version ใหม่ๆ จะมี python3 ติดตั้งมาให้ โดย default อยู่แล้ว
- สำหรับ Mac สามารถทำตาม Tutorial นี้ เพื่อติดตั้งได้
หลังจากติดตั้งแล้วบน Windows พิมพ์คำสั่ง $ py
บน Linux, Mac พิมพ์คำสั่ง $ python3
จะต้องได้หน้า python console ออกมาเหมือนในรูปด้านล่างนี้

ตัวอย่าง Python3 console
2. ติดตั้ง pip3
pip3 คือ package manager ที่ใช้สำหรับติดตั้ง package เสริมให้กับ Python3 (คล้ายๆ คำสั่ง apt-get บน linux) โดยเราจะใช้ pip ในการติดตั้ง Django ต่อไป
- สำหรับ Windows คำสั่ง pip จะถูกติดตั้งมาอยู่แล้วบน python version 3.5 ขึ้นไป
- สำหรับ Linux ติดตั้งด้วยคำสั่ง $ sudo apt-get install python3-pip
- สำหรับ Mac ทำตาม Link ด้านบนเพื่อติดตั้ง pip3
เมื่อติดตั้งเสร็จสิ้นทดสอบด้วยการพิมพ์คำสั่ง $ pip3 ใน console

3. ติดตั้ง Django
พิมพ์คำสั่ง $ pip3 install django==1.11.5
แล้ว pip3 จะ download django เข้ามาติดตั้งในเครื่องให้โดยอัตโนมัติ


ตัวอย่างการติดตั้ง Django
4. ตรวจสอบการติดตั้ง โดยพิมพ์คำสั่ง $ django-admin ตามรูปด้านล่าง


ตัวอย่างการเรียกคำสั่ง django-admin เพื่อแสดง Django version ที่ติดตั้ง
NOTE: สำหรับ Linux user อาจเจอ Error

The program ‘django-admin’ is currently not installed. You can install it by typing:

sudo apt install python-django-common

ซึ่งหมายความว่าคำสั่ง django-admin ยังไม่ได้อยู่ใน PATH environment variable ให้ค้นหา Path ของ django-admin ด้วยคำสั่ง $ find / -name django-admin.py
ซึ่งโดยปกติแล้ว path จะอยู่ที่ /home/<user>/.local/bin/django-admin.py เช่น


ตัวอย่างการเรียกคำสั่ง django-admin บน Linux
สร้าง Django Project
Browse ไปยัง Folder ที่ต้องการเก็บ project จากนั้น เริ่มสร้าง project ชื่อ “my_library” (ห้องสมุดของฉัน) ด้วยคำสั่ง

$ django-admin startproject my_library

จะทำให้ได้โฟลเดอร์ my_library ซึ่งด้านในจะเก็บไฟล์ project ของ Django ดังนี้


โครงสร้างโฟลเดอร์ของ Django Project
manage.py คือไฟล์ script สำหรับรันคำสั่งต่างๆ ที่เกี่ยวข้องกับ Django โดยปกติไฟล์นี้จะไม่ถูกแก้ไขใด ๆ ทั้งสิ้น
__init__.py คือไฟล์ว่างๆ (ลองเปิดด้วย text editor ดูได้นะครับ) ไฟล์นี้มีไว้เพื่อให้ภาษา Python รู้ว่าโฟลเดอร์ที่อยู่นี้เป็นโฟลเดอร์ที่ใช้เก็บ Python Package โดยปกติไฟล์นี้จะถูกปล่อยเป็นไฟล์ว่าง ๆ ไว้แต่เราสามารถใส่ Python script เข้าไปได้เช่นกันแต่จะไม่ขอพูดถึงรายละเอียดในส่วนนี้ในบทความนี้ โดยรายละเอียดเพิ่มเติมของไฟล์นี้สามารถศึกษาได้จาก ที่นี่
settings.py คือไฟล์ที่ใช้เก็บ configuration ทั้งหมดของ project เอาไว้ เช่น การตั้งค่า Database, Timezone, Logging เป็นต้น ซึ่งค่าที่เก็บในนี้จะอยู่ในรูปแบบ key — value ซึ่งไฟล์นี้จะเป็นไฟล์แรกที่ Django เข้ามาอ่านเมื่อเริ่มการทำงานของ web server
urls.py คือไฟล์ที่ใช้เก็บการ routing ของ HTTP request ซึ่งจะกล่าวถึงในหัวข้อถัดไป
wsgi.py คือไฟล์ที่ใช้เก็บข้อมูลของ Django project ของเรา ใช้สำหรับการ deploy project เมื่อต้องการเชื่อมต่อกับ Web Server สำหรับรายละเอียดการ deploy สามารถอ่านเพิ่มเติมได้ ที่นี่ หรือ ที่นี่
ทดลองรัน Django Project ที่ port 8000 ด้วยคำส่ัง

$ py manage.py runserver 0.0.0.0:8000

หรือ สำหรับ Linux ให้รันคำสั่ง

$ python3 manage.py runserver 0.0.0.0:8000


ตัวอย่างการรัน Django project ครั้งแรก
ซึ่งคำสั่งที่ใช้จะแบ่งเป็น


คำสั่งที่ใช้สั่งรัน Django Project
py manage.py คือการสั่งรัน Python script ในไฟล์ manage.py ซึ่งเป็นคำสั่งเริ่มต้นในการรัน Django command ทุกคำสั่ง
runserver คือ parameter เพื่อบอกว่าต้องการ start web server ขึ้นมา
0.0.0.0:8000 คือ parameter ของ web server ที่เราจะสร้างขึ้นมา โดย 0.0.0.0 หมายถึงให้ web server ของเรา bind กับทุก ๆ IP ในเครื่องของเรา และ 8000 คือ port ที่ต้องการรัน
หลังจากรัน Django project สำเร็จ สามารถทดลองใช้ web browser เปิดเข้าหน้าเวปของเราได้ที่ http://localhost:8000 จะได้ผลลัพธ์ตามภาพด้านล่าง


หน้า web ที่เห็นหลังจากสร้าง Django project และรันสำเร็จ
การรันคำสั่ง runserver จะส่งผลให้ Django ไปอ่าน configuration ในไฟล์ settings.py แล้วเริ่ม start web server ด้วย configuration เหล่านั้น โดยค่า config ที่อยู่ในไฟล์ settings.py มีรายละเอียดดังต่อไปนี้

BASE_DIR คือตัวแปรที่เก็บ absolute path ไปหา Django project ของเรา ซึ่งโดยปกติข้อมูลส่วนนี้จะถูกเขียนอยู่ในรูปแบบของ Python script ที่ใช้อ้าง path มาถึงไฟล์ settings.py ตัวนี้ (สามารถทดลองโดยการ copy code ดังกล่าวมา save ไว้ในไฟล์ python ที่สร้างมาใหม่แล้วลองรันดูผลลัพธ์ได้)
SECRET_KEY คือตัวแปรที่ใช้เก็บ hash text ใช้สำหรับการเข้ารหัสสิ่งต่าง ๆ ใน Django project เช่น session, cookies, password เป็นต้น ดังนั้นจึงไม่ควรเปลี่ยนค่านี้ และเก็บไว้เป็นความลับไม่ copy ไปแสดงในที่อื่น (โดยปกติค่านี้จะไม่ถูกแก้ไขหรือใช้งานอยู่แล้ว จะถูกใช้งานโดยอัตโนมัติเอง)
DEBUG คือตัวแปรที่ใช้บอก Django ว่ารันใน mode debug หรือไม่ ซึ่งใน mode debug นี้ Django จะแสดง Error stack traceทั้งหมดออกมาในหน้าจอ web browser เพื่อให้ developer เห็นบรรทัดที่ code error แล้วเข้าแก้ไขได้ทันที
ALLOWED_HOSTS คือตัวแปรที่ใช้เก็บชื่อ domain name ของ web site เรา โดยจะเก็บในรูปแบบ list ของ string เช่น [‘www.mylibrary.com’, ‘128.199.148.2XX’] เหตุผลที่ต้องระบุชื่อของ host อย่างเจาะจงเพื่อนำไปสร้าง host header ใน HTTP request เพื่อใช้ป้องกัน Cross Site Scripting attack ที่มีการส่ง host ปลอมมาหลอก server เราได้
INSTALLED_APPS คือตัวแปรที่ใช้เก็บ Django Application ทั้งหมดที่ project นี้จะรู้จัก ซึ่งโดย default Django จะ add default Django Application บางตัวเข้ามาอยู่แล้ว
MIDDLEWARE คือ plugin ที่ถูกใช้งานโดย Django เพื่อใช้ในงานด้านต่าง ๆ เช่น django.contrib.auth.middleware.AuthenticationMiddleware ถูกใช้สำหรับการจัดการ user ที่ authenticated กับระบบเข้ากับ HTTP request โดยผ่านทาง session ที่ user นั้น ๆ login อยู่เป็นต้น ซึ่งโดยปกติ Django จะมีการ add middleware ที่จำเป็นมาให้อยู่แล้ว
ROOT_URLCONF คือตัวแปรที่ใช้เก็บ path ไปหาไฟล์ urls.py ซึ่งเป็นไฟล์แรกที่ Django เริ่มทำงานเมื่อได้รับ HTTP request
TEMPLATES คือตัวแปรที่เก็บ configuration ของ Template โดย Template คือสิ่งที่รับผิดชอบในการ render หน้าเวป HTML + javascript ออกมาแล้วส่งกลับไปให้ web browser ซึ่งจะกล่าวถึงในหัวข้อถัดไป
WSGI_APPLICATION คือตัวแปรที่ใช้เก็บ path ไปหาตัวแปร wsgi application ซึ่งถูกใช้ในการ deploy ระบบใน environment จริง เมื่อต้องการเชื่อมต่อ Django เข้ากับ web server ต่าง ๆ
DATABASES คือตัวแปรที่เก็บ configuration ต่าง ๆ ของ ฐานข้อมูล เช่น ชนิดของฐานข้อมูล, username, password, ชื่อ database เป็นต้น โดย default Django จะใช้ sqlite3 ซึ่งเป็นฐานข้อมูลชนิดไฟล์ในการทำงาน
LANGUAGE_CODE คือตัวแปรที่ใช้เก็บภาษา default ที่ระบบจะแสดงผล
TIME_ZONE ใช้เก็บ timezone ตามปกติ
USE_I18N คือตัวแปรที่ใช้บอกว่าระบบรองรับ I18N (Internationalization)หรือไม่ ซึ่ง I18N คือระบบการแปลภาษาในหน้าเวปไซด์ให้รองรับหลาย ๆ ภาษา หลักการทำงานคือ Django จะสร้างไฟล์ขึ้นมาเป็น list ของ text ทั้งหมดในหน้าเวปเรา แล้วให้เราแปล text เหล่านี้ให้อยู่ในภาษาอื่น ๆ เท่าที่เราต้องการจะ support แล้ว Django จะนำ text ที่แปลแล้วมาแสดงแก่ผู้ใช้งานอีกทีหนึ่ง
USE_L10N คือตัวแปรที่บอกว่า web server ของเรา support L10N (Localization) หรือไม่ ซึ่ง L10N จะแตกต่างกับ I18N คือ I18N จะครอบคลุมถึงการแปลภาษาบนหน้าจอเท่านั้น ส่วน L10N จะมีส่วนไปถึงการแสดงผลต่าง ๆ เช่น รูปแบบการแสดงวันที่, การแสดงหน่วยของเงิน เป็นต้น
USE_TZ คือตัวแปรที่ใช้เก็บว่า web server รองรับ Time zone หรือไม่ หากตั้งค่าเป็น false ระบบจะไม่สนใจค่า time zone และใช้เวลาตามเครื่อง server เป็นหลักโดยไม่มีการทดเวลา เหมาะสำหรับการพัฒนาเวปไซด์ที่มีผู้ใช้งานเป็นคนไทย และไม่จำเป็นต้องใช้กับต่างประเทศ
STATIC_URL คือตัวแปรที่ใช้เก็บ web url ไปยัง folder ที่ใช้เก็บ static ไฟล์ต่าง ๆ เช่น http://www.mylibrary.com/static/ เป็นต้น
STATIC_ROOT ตัวแปรนี้ไม่ได้ถูกสร้างมาโดย default เป็นตัวแปรที่ใช้สำหรับเก็บ path ที่เราไว้เก็บไฟล์ static ต่าง ๆ เช่น ไฟล์ javascript หรือ css
สร้าง Django Application
Django framework แนะนำให้แบ่งการพัฒนา web application ของเราออกเป็น module ย่อย ๆ แทนที่จะเก็บใน folder project ใหญ่ ๆ เพียงตัวเดียว โดย module ย่อย ๆ เหล่านี้เรียกว่า Django Application ซึ่งข้อกำหนดในการแบ่ง Django Application นั้น ไม่มีแบบแผนที่ตายตัว ขึ้นอยู่กับความเหมาะสมของแต่ละ project เช่น project my_library (ห้องสมุดของฉัน) อาจสามารถแบ่ง Django Application ออกเป็น

book_management ใช้สำหรับจัดการหนังสือในห้องสมุด เช่น การลงทะเบียนหนังสือ, การค้นหาหนังสือ, การจัดการยืมคืน เป็นต้น
human_resource ใช้สำหรับจัดการพนักงานที่ทำงานในห้องสมุดแห่งนี้ เช่น การลงทะเบียนพนักงาน, การจัดกะการทำงาน, การลงเวลาเข้าออกพนักงาน
account ใช้สำหรับเก็บบัญชีรายรับ, รายจ่ายของห้องสมุดแห่งนี้ เป็นต้น
สำหรับคำสั่งที่ใช้ในการสร้าง Django Application ที่ชื่อ book_management คือ

$ py manage.py startapp book_management


โครงสร้างโฟลเดอร์ของ Django Application
โดยแต่ละไฟล์จะค่อย ๆ อธิบายผ่านบทความนี้ไปเรื่อย ๆ ครับ

ความต้องการขั้นต่ำที่สุดของ Django คือไฟล์ urls.py และ views.py

เริ่มจากไฟล์ views.py เป็นไฟล์ที่ใช้เก็บ logic ของ web application คอยควบคุมสิ่งที่รับมาจาก client web browser (HTTP parameters ต่าง ๆ) และควบคุมสิ่งที่จะตอบกลับไปยัง client web browser

ทดลองเปิดไฟล์ views.py ด้วย text editor แล้วเพิ่ม function ลงไปครับ


ตัวอย่างไฟล์ views.py
จากนั้นแก้ไขไฟล์ urls.py ให้เป็นดังรูป


ตัวอย่างไฟล์ urls.py
จากนั้นรัน Django อีกครั้ง แล้วเปิด web browser แล้วเข้าหน้าเวป http://localhost:8000/my_index/ จะเห็นว่าหน้าจอที่แสดงผลเปลี่ยนเป็นดังรูปด้านล่างนี้


ตัวอย่างหน้า Web Page แรก
สิ่งที่เกิดขึ้นภายในการทำงานของ Django สามารถอธิบายได้ด้วยภาพดังต่อไปนี้


การทำงานของ Django เมื่อได้รับ HTTP Request จาก Web Browser
เมื่อได้รับ HTTP Request จาก Web Browser มาแล้ว Django จะเริ่มทำงานโดยเริ่มจากไฟล์ urls.py ซึ่งหน้าที่หลักของไฟล์นี้คือการทำ URL Pattern Matching เพื่อดูว่า user request มาที่ URL อะไร จากนั้นจึงค่อยเรียก Python Script ที่ถูก match เพื่อขึ้นมาทำงาน


อธิบายการทำงานของ urls.py
จากรูปจะเห็นว่าข้อมูลใน urls.py ถูกแบ่งออกเป็นสองส่วนนั่นคือ

r’^my_index/$’ ส่วนนี้เป็น String ที่ใช้ระบุถึง Regular Expression ที่จะใช้ match กับ URL ที่ผู้ใช้กรอกมาใน Web Browser
NOTE: ตัว r ด้านหน้า String ใน Python หมายถึง “Raw String Literal” คือให้มอง String ทั้งหมดโดย ignore สัญลักษณ์พิเศษ นั่นคือ backslash (\) ทำให้ Python มอง backslash ว่าเป็นตัวอักษรธรรมดาตัวหนึ่งไม่ใช่ escape character ดังนั้น r’\n’ จะไม่มีผลให้ขึ้นบรรทัดใหม่แต่จะหมายถึงตัวอักษรว่า \n จริง ๆ
views.index คือ Python Script ที่อ้างไปถึงไฟล์ views.py ในโฟลเดอร์ book_management และไปยัง function ที่ชื่อ index ซึ่งจะเห็นว่าในไฟล์ views.py จะมีการเรียก function HttpResponse() เพื่อ return HTML text กลับไปแสดงผลบนหน้าจอ

อธิบายการทำงานไฟล์ views.py
เป็นส่วนที่ใช้ import function ชื่อ render และ HttpResponse เข้ามาใช้งานใน Script ของเรา
การประกาศ function ของ Python เป็น function ชื่อ index โดยรับ parameter เป็น request ซึ่ง parameter นี้มีชนิดตัวแปรเป็น HttpRequest Object ซึ่งภายในตัวแปรนี้จะเก็บข้อมูลต่าง ๆ ของ HTTP เอาไว้ เช่น HTTP parameter, method, content type, body, หรือ path เป็นต้น
ประกาศตัวแปรชนิด HttpResponse ซึ่งจากตัวอย่างเราจะส่ง body ของ response เป็น HTML ง่าย ๆ กลับไปแสดงผลยัง Web Browser
Django Template
จากตัวอย่างในหัวข้อก่อนหน้าจะเห็นว่าเราสามารถส่ง HTML กลับไปยัง Web Browser ได้โดยผ่านทาง views.py แต่หากเราต้องการส่งหน้า HTML ที่มีความซับซ้อนมากกว่านี้ เช่น มีการแนบไฟล์ Javascript, CSS, หรือภาพ หรือแม้แต่หน้า web site แบบ AngularJS หรือ React กลับไปแสดงผลบน Web Browser จะมีความยุ่งยากมากหากใช้วิธีนี้่ที่ต้องเปลี่ยน library เหล่านั้นเป็น text เพื่อกลับไปแสดงผล ซึ่ง Django มีวิธีที่ใช้ในการส่งหน้า Web Page ที่มีความซับซ้อนโดยผ่านทาง Template Engine


ตัวอย่างอธิบายการทำงานของ Django Template
จากรูปจะเห็นว่าในการทำงานของ Template นั้นเริ่มจากทางผู้พัฒนาต้องสร้างไฟล์ HTML Template ขึ้นมา ซึ่งสิ่งทีทำให้ไฟล์ HTML นี้ต่างจากไฟล์ HTML ทั่วไปคือจะมีการฝัง Django Tag เข้าไปด้วย โดยในตัวอย่างคือการใช้ {{var1}} หมายถึงการสร้างตัวแปรของ Django ขึ้น จากนั้นเมื่อ Django โหลดไฟล์ Template นี้ขึ้นมาสามารถ pass ค่า ของตัวแปรเข้าไปสู่ไฟล์นี้ได้ หลังจากนั้นจึงได้ไฟล์ HTML ที่สมบูรณ์พร้อมส่งกลับไปแสดงผลยัง Web Browser ต่อไป

Django Tag ที่สามารถใช้งานได้มีหลากหลาย เช่น การส่งผ่านตัวแปรธรรมดาดังตัวอย่างด้านบน, การใช้ if/else, การใช้ for loop ซึ่งรายละเอียดของ Django Tag ทั้งหมดสามารถ อ่านเพิ่มเติมได้ที่นี่

เริ่มการทดลองนี้โดยการสร้าง Folder Template และสร้างไฟล์ index.html


สร้างโฟลเดอร์ชื่อ templates และสร้างไฟล์ index.html ในนั้น

code ในไฟล์ index.html
จากนั้นแก้ไขไฟล์ settings.py โดยการเพิ่ม ค่าให้กับตัวแปร DIRS ที่อยู่ภายใต้ TEMPLATES configuration ซึ่ง DIRS จะเป็นตัวบอกว่าไฟล์ HTML template ของเราถูกเก็บไว้ที่ไหนบ้าง


ไฟล์ settings.py ที่ถูกแก้ไขเพื่อให้ Django รู้จัก Folder Template
จากนั้นแก้ไขไฟล์ views.py โดยเพิ่มเติม code ดังต่อไปนี้


ไฟล์ views.py ที่ใช้ในการโหลด HTML Template ชื่อ index.html แล้วผ่านค่าตัวแปร var1 ลงไป
เพิ่ม import ตัวแปร loader
ประกาศตัวแปรชื่อ header_str ให้เป็นชนิด String และมีข้อความดังปรากฎในรูป
โหลด template ไฟล์ชื่อ index.html โดย Django จะพยายามไปหาจาก path ที่เรากรอกไว้ใน DIRS
ประกาศตัวแปร context เป็นชนิด dictionary (dictionary คือ datatype ที่ใช้เก็บตัวแปรในรูปแบบของ key, value) โดยมีค่า key เป็น var1 ซึ่งเป็นชื่อตัวแปรที่ประกาศใน index.html และ value คือตัวแปร header_str
เรียกฟังก์ชั่น render เพื่อ generate HTML ไฟล์ออกมาเพื่อส่งให้กับ Client
เปิด Web Browser แล้ว Browse ไปยัง http://localhost:8000/my_index/


ตัวอย่างผลลัพธ์ของหน้าจอ HTML
เราสามารถย่อ code ที่ใช้ในการ load template ด้วยฟังก์ชั่น render ได้ดังรูปต่อไปนี้


การเรียกใช้ฟังก์ชั่น render เพื่อย่อ code ที่ใช้ในการ load Django Template
การโหลด Javascript, CSS, หรือรูปภาพมาใช้งานบนหน้า web page

กรณีที่เราต้องการใส่ Javascript, CSS หรือรูปเข้าไปเพื่อแสดงผลในหน้าเวป สามารถทำได้โดยผ่าน static (ที่เรียกว่า static เพราะไฟล์ JS, CSS, images เป็นไฟล์ Library ที่คงที่ ไม่มีการเปลี่ยนแปลง) โดยการใช้งาน static feature ใน Django นั้นต้องเริ่มจากไฟล์ settings.py ตรวจสอบว่ามี 2 บรรทัดนี้อยู่ในไฟล์


Configuration ที่ทำให้เกิด Feature Static
จากนั้นเพิ่ม Folder ชื่อ static ภายใต้ Folder book_management และสร้างไฟล์ style.css ขึ้นมา ซึ่ง Django จะไปหาไฟล์ static ตาม path static ที่อยู่ภายใต้ Django Application folder โดยอัตโนมัติ


สร้างโฟลเดอร์ static และ style.css

แก้ไขไฟล์ style.css โดยเพิ่มข้อความดังต่อไปนี้ (เป็นการเปลี่ยนพื้นหลังให้เป็นสีเหลือง)
จากนั้นแก้ไขไฟล์ index.html โดยเพิ่มบรรทัดดังต่อไปนี้เข้าไป


หมายถึงการ load library static ของ Django เข้าไปใน web browser
การเรียกใช้ CSS ภายในหน้าเวป โดยให้สังเกตุ tag href จะมีการเรียกใช้ Django syntax ชื่อ static
จากนั้น browse ไปที่ http://localhost:8000/my_index/ จะได้ผลลัพธ์ดังต่อไปนี้


ภาพผลลัพธ์การ load static ไฟล์จาก Django
จากตัวอย่างข้างต้นสามารถใช้วิธีเดียวกันนี้ไปประยุกต์ใช้กับการโหลด Javascript และรูปภาพได้ เช่น

<img src=“{% static ‘background.png’ %}”/> เพื่อ โหลดรูปขึ้นมาแสดงผล
<script src=“{% static ‘myscript.js’ %}”/> เพื่อโหลด Javascript Library เข้ามาใช้งาน
การเชื่อมต่อฐานข้อมูล
การเข้าถึงฐานข้อมูลของ Django นั้นโดยทั่วไปจะไม่ใช้ SQL statement ตรง ๆ แต่จะถูกกระทำผ่านสิ่งที่เรียกว่า Object Relational Mappings (ORM) ซึ่ง ORM จะเป็นซ่อนคำสั่งของ SQL statement ทั้งหมดออกจากการพัฒนา แต่จะให้ผู้พัฒนาเข้าถึงฐานข้อมูลผ่านทาง class — object แทน (class/object เหมือนใน OOP ทั่วไป)โดย class จะเป็นตัวแทนของ Table ในฐานข้อมูล และ object จะเป็นตัวแทนของข้อมูลในฐานข้อมูล (Record)

ข้อดีของการใช้ ORM คือ syntax สามารถอ่านได้ง่ายกว่า SQL statement, และเราสามารถเปลี่ยนฐานข้อมูลได้โดยง่าย เช่น จากเดิมใช้ SQLite3 ต้องการเปลี่ยนเป็น MySQL หรือ Postgres ก็สามารถทำได้ทันที (อาจมีบางคำสั่งไม่ compatible กันซะทีเดียว ต้องมีการทดสอบให้ดีหลังเปลี่ยนฐานข้อมูลแล้วนะครับ)

ฐานข้อมูลที่จะใช้ในการทดสอบในครั้งนี้คือ SQLite3 ซึ่งเป็นฐานข้อมูลชนิดไฟล์ ซึ่งถูกตั้งค่าไว้เป็น default สำหรับ Django เราสามารถเปลี่ยนแปลงค่านี้ได้ทีหลังในไฟล์ settings.py


ไฟล์ settings.py แสดงการตั้งค่าฐานข้อมูล SQLite3 ซึ่งติดตั้งมาเป็นค่า default
ในหัวข้อนี้เราจะทดลองสร้างฐานข้อมูลที่เก็บข้อมูลของหนังสือ (Book) โดยหนังสือแต่ละเล่มจะถูกจัดอยู่ในหมวดหมู่ (Category) ต่างๆ ดังตัวอย่างต่อไปนี้


ตัวอย่างฐานข้อมูลที่ต้องการสร้าง
ซึ่งสามารถทำได้โดยการแก้ไขไฟล์ models.py ในโฟลเดอร์ book_management ดังต่อไปนี้


ตัวอย่างไฟล์ models.py สำหรับสร้างฐานข้อมูลที่มี table ชื่อ Book และ Category
Import models object ซึ่งตัว models นี้เป็นพื้นฐานสำหรับการทำให้ class ของเรามีรูปแบบที่ ORM สามารถรู้จักได้
ประกาศ class ชื่อ Category ซึ่งสืบทอด (inherit) มาจาก class models.Model ส่วนนี้จะเป็นการบอกว่าให้สร้าง table ชื่อ Category ขึ้นในฐานข้อมูล
ประกาศตัวแปรชื่อ name เป็นชนิด CharField มีความยาวสูงสุด 255 ตัวอักษร ส่วนนี้จะเหมือนกับการประกาศ Database Field ชื่อ name มีชนิดเป็น varchar 255 นั่นเอง
ประกาศ class ชื่อ Book เป็นการสร้าง table ชื่อ Book ขึ้นมา
ประกาศตัวแปร title เป็นชนิด CharField
ประกาศตัวแปร publish_date เป็นชนิด date time ใช้เก็บวันที่ตีพิมพ์
ประกาศตัวแปร category เป็นตัวแปรที่มีความสัมพันธ์ Foreign Key ไปหา table Category โดย parameter ที่ชื่อ on_delete=models.CASCADE หมายถึงการบอกว่าหาก Category Object ถูกลบไป Django จะตามไปลบ Book ทุกตัวที่มี Reference ถึง Category นี้ด้วย
สำหรับรายละเอียดชนิดของตัวแปร (Database Field) ทั้งหมดที่ Django support สามารถอ่านเพิ่มเติมได้ ที่นี่

แก้ไขไฟล์ settings.py เพื่อให้ Django project รู้ว่ามี Django Application ที่มีฐานข้อมูลได้โดยเพิ่ม ‘book_management’ เข้าไปในส่วนของ INSTALLED_APPS ดังแสดงในรูปด้านล่าง (อย่าลืมใส่ลูกน้ำ (,) ไว้หลังบรรทัด ‘django.contrib.staticfiles’ ด้วยนะครับ) โดยการเขียนอย่างนี้หมายถึงตัวแปร INSTALLED_APPS จะเป็นตัวแปรที่เก็บ list ของ string เอาไว้


เพิ่ม Django Application ให้กับ Django Project รู้จัก
ในการสร้างฐานข้อมูลจริง ๆ นั้น Django จำเป็นต้อง generate script ออกมาชุดหนึ่ง เรียกว่า Migration File ไว้ใช้สำหรับการสร้างฐานข้อมูลจริง ประโยชน์ของ Migration File ทีสร้างขึ้นมานี้เพื่อให้ Django Application สามารถ track การเปลี่ยนแปลงของฐานข้อมูลได้ตลอดเวลาที่มีการเปลี่ยนแปลง models.py ซึ่ง Django สามารถเปลี่ยน schema ของฐานข้อมูลไปมาได้ หรือจะย้อนกลับไปใช้ schema เก่าได้อย่างง่ายดาย (ในความเป็นจริงหากฐานข้อมูลมีความซับซ้อนมาก ๆ กระบวนการย้อน schema กลับไปก็เป็นสิ่งที่ยากเหมือนกันครับ)


การทำงานของ Django ORM เพื่อใช้สร้าง Database Schema
โดยคำสั่งที่ใช้ในการสร้าง Migration File คือ

$ py manage.py makemigrations


ตัวอย่างการรันคำสั่ง makemigrations
หลังจากรันคำสั่งนี้จะส่งผลให้เกิดไฟล์ใหม่ขึ้นมาภายใต้โฟลเดอร์ book_management/migrations คือไฟล์ 0001_initial.py


สำหรับ Migration File ที่สร้างขึ้นมานี้หากลองเปิดดูจะเห็นว่าเป็นชุดคำสั่งของ Python ที่ใช้สำหรับเปลี่ยนแปลง Schema ในฐานข้อมูล โดยปกติแล้วผู้พัฒนาไม่จำเป็นต้องแก้ไขไฟล์นี้ แต่มีบางกรณีเช่นกันที่ต้องเข้ามาแก้ไข เช่น ต้องการลบ table A พร้อมกับย้ายข้อมูลบางส่วนไปยัง table B เป็นต้น

จากนั้นสั่งให้ Django สร้างฐานข้อมูลด้วยคำสั่ง

$ py manage.py migrate


ตัวอย่างการรันคำสั่ง migrate เพื่อสร้างฐานข้อมูล
หลังจากรันไฟล์นี้แล้วเราจะได้ไฟล์ใหม่ชื่อ db.sqlite3 ซึ่งเป็นไฟล์ฐานข้อมูลที่มี table ของ Book และ Category อยู่ภายใน และ Django จะทำการสร้าง Table Default อื่นๆ ขึ้นมาด้วย เช่น Table User, role สำหรับการทำ Authentication เป็นต้น


โครงสร้างฐานข้อมูลที่ถูกสร้างขึ้นโดย Django
Django Shell
Django Shell คือ python shell แบบหนึ่งซึ่งสามารถเข้าใช้งานฐานข้อมูลได้ ซึ่งเป็น feature ที่สะดวกมากในการเข้าตรวจสอบ debug ฐานข้อมูล หรือทดสอบใส่ข้อมูลเข้าไปในฐานข้อมูลโดยตรง โดยเราสามารถเข้าถึง Django Shell ด้วยคำสั่ง

$ py manage.py shell


ตัวอย่าง Django Shell
ขั้นตอนต่อไปเป็นการ import table ของฐานข้อมูลให้กับ shell รู้จัก เพื่อเตรียมตัวทำงานกับ table เหล่านี้ต่อไป

from book_management.models import Category, Book

จากนั้นทดลองสร้าง Category ของหนังสือ ชื่อ “Horror” ด้วยคำสั่ง

horror_category = Category(name=’Horror’)
horror_category.save()


แสดงขั้นตอนการสร้าง Category Horror ในฐานข้อมูล
จะเห็นว่าการสร้าง Record ใน Database Table นั้นสามารถทำได้อย่างง่าย คล้ายกับการสร้าง object ของ class ตามปกติ โดยในบรรทัดแรกจะเป็นคำสั่งที่ใช้ในการสร้าง object ชื่อ horror_category จาก class Category โดยมี parameter name เป็น Horror และบรรทัดที่สองคำสั่ง save() เป็นฟังก์ชั่นที่ให้ Django เปิดการเชื่อมต่อกับฐานข้อมูลและ save Record ลงฐานข้อมูลจริง


ทดสอบ Browse ฐานข้อมูลจริงเพื่อดูข้อมูลในฐานข้อมูล
จากรูปจะเห็นว่าในฐานข้อมูลจริงนั้น Django ได้ใส่ Record ที่ชื่อ Horror เข้าไปในฐานข้อมูล และสังเกตุ Field ชื่อ id เป็น Field Default ที่ถูกสร้างขึ้นโดย Django เพื่อใช้เป็น internal key สำหรับเป็น primary key ของ table นี้ เนื่องจากในทุก ๆ table ในฐานข้อมูล Django จะบังคับให้มี primary key อย่างน้อย 1 ตัว ดังนั้นหากเรากำหนด primary key ตอนประกาศ class จะทำให้ Field id นี้หายไป

ทดลองดึงข้อมูลออกจากฐานข้อมูลด้วยคำสั่ง

c_list = Category.objects.filter(name=’Horror’)
c_list[0].name


ผลลัพธ์การดึง Category ออกจากฐานข้อมูล

ประกาศตัวแปรชื่อ c_list ไว้รอรับค่าจากการเรียกฟังก์ชั่น
Category.objects จะ return object ชนิด Manager ออกมา ซึ่งเป็น object ที่ใช้เริ่มต้นในการทำ Database operation ต่าง ๆ ต่อไป
ฟังก์ชั่น filter คือฟังก์ชั่นที่ใช้ในการค้นหาข้อมูลในฐานข้อมูล เทียบเท่ากับคำสั่ง SELECT ในภาษา SQL ธรรมดา ซึ่งจากในตัวอย่างเราสามารถแปลงเป็น SQL statement ได้ว่า SELECT * FROM Category WHERE name=’horror’ นั่นเอง สิ่งที่ return กลับมาจากฟังก์ชั่น filter คือ QuerySet object ซึ่งเป็น list ของ object (Record ในฐานข้อมูล) ที่ได้จากคำสั่งต่างๆ นั่นเอง สำหรับรายละเอียดคำสั่ง Query อื่น ๆ เช่น order_by, like สามารถอ่านเพิ่มเติมได้จาก ที่นี่
เราสามารถนำความรู้ที่ได้จากส่วนนี้มาใช้ร่วมกับไฟล์ template และ views.py เพื่อส่งผลลัพธ์ที่ได้จากฐานข้อมูลกลับไปให้ผู้ใช้งานได้เห็นได้ เริ่มจากทดลองแก้ไขไฟล์ templates/index.html ดังต่อไปนี้


แก้ไขไฟล์ index.html เพื่อแสดงผลการนับ Category object และ Book object จากฐานข้อมูล
จากนั้นแก้ไขไฟล์ views.py ดังต่อไปนี้


ไฟล์ views.py ที่แก้ไขเพื่อแสดงค่าการนับ Category และ Book ในฐานข้อมูล

len() เป็น function build-in ของ Python โดยรับค่าตัวแปรเป็น list แล้วจะ return มาเป็นจำนวน element ทั้งหมดที่อยู่ใน list โดยจากตัวอย่างเราได้ส่งผลลัพธ์ของการ Query หรือ QuerySet เข้าไป ทำให้ len return ค่าของจำนวน Record ทั้งหมดใน QuerySet นี้ออกมา
all() เป็น Manager Function ที่ใช้สำหรับ Select ทุกอย่างออกมาจาก Table ซึ่งจากคำสั่งด้านบนสามารถแปลงเป็น SQL Statement ได้ว่า SELECT * FROM Category นั่นเอง
จากนั้นทดลอง Browse หน้าเวปไปที่ http://localhost:8000/my_index/ จะได้ผลลัพธ์ดังรูปต่อไปนี้


Django admin site
อีกหนึ่ง Feature เด่นสำหรับ Django คือหน้า Web Page ซึ่งเป็นหน้าสำหรับใช้ในการทำ Database CRUD operation (Create, Read, Update, Delete) เหมาะสำหรับใช้เป็นหลังบ้านสำหรับ Web Admin ใช้บริหารงานต่าง ๆ โดยไม่ต้องเข้าถึงฐานข้อมูลโดยตรง หรือสามารถใช้ในการ debug ข้อมูลได้อย่างรวดเร็วอีกด้วย และยิ่งไปกว่านั้น Django Admin ยังสามารถปรับแต่งแก้ไขให้แสดงรายละเอียดตามที่ต้องการได้หลากหลาย เช่น ต้องการใส่ search box, ใส่ filter เปลี่ยนการแสดงผล เช่น Object Book ต้องการแสดงแค่ชื่อของหนังสือเพียงอย่างเดียว เป็นต้น

การใช้งาน Django Admin นั้นขอให้ตรวจสอบไฟล์ settings.py และแก้ไขไฟล์ urls.py ให้มีค่าตามที่แสดงในรูปด้านล่างนี้


ไฟล์ settings.py โดยปกติค่าเหล่านี้จะใส่มาให้โดย default อยู่แล้ว

ไฟล์ urls.py แก้ไขโดยเพิ่มบรรทัดที่ highlight ด้วยกรอบสีแดงทั้งสองบรรทัด
จากนั้นลองใช้ web browser เข้าไปที่ URL : http://localhost:8000/admin/ จะได้ผลลัพธ์ดังรูปต่อไปนี้


จะเห็นว่าเรายังไม่สามารถเข้าใช้งานหน้า Admin ได้เนื่องจากติด Authentication ให้ทำการเพิ่ม user ด้วยคำสั่งดังรูปต่อไปนี้


การสร้าง Super User เพื่อเข้าถึงหน้า Django admin site
จากนั้นกลับไป Login เพื่อเข้าสู่หน้าจอ Django admin site


จากรูปจะเห็นว่าเราสามารถแก้ไขได้เพียงแค่ Table ที่เกี่ยวกับ user และ group แต่จะไม่เห็น Table Book หรือ Category เนื่องจาก Django admin ยังไม่รู้จัก Table ทั้งสองของเรา ซึ่งเราสามารถทำให้ Django รู้จัก Table ของเราได้โดยผ่านทางไฟล์ admin.py



แก้ไขไฟล์ admin.py โดยเพิ่ม สองบรรทัดนี้เข้าไป
จากนั้นเปิดหน้า web admin ใหม่อีกครั้งจะเห็น Book และ Category ขึ้นมา




จะเห็นว่าการแสดงผลของ Category จะพิมพ์คำว่า Category Object ออกมา เนื่องจาก Django ไม่ทราบว่าเมื่อ object ของ class Category ถูกแปลงเป็น String แล้วจะแสดงผลอย่างไร สามารถแก้ไขตรงนี้ได้โดยการ override function โดยการแก้ไขไฟล์ models.py ดังต่อไปนี้


การประกาศฟังก์ชั่นภายใน class ของ python จะถูกบังคับให้ใส่ตัวแปรชื่อ self มาเสมอ ซึ่งตัวแปร self จะหมายถึง object ของตัวเอง (เหมือนกับ keyword “this” ใน java หรือ C#) ส่วนฟังก์ชั่นที่ประกาศเพิ่มคือ __str__ จะเหมือนกับฟังก์ชั่น toString() ใน Java นั่นเอง
