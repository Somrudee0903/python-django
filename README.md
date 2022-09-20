# python-django
 Django-Tutorial — the tutorial for DjangoPython
 
ภาษา Python เริ่มถูกใช้งานอย่างแพร่หลายมากขึ้นเรื่อยๆ ในช่วงนี้เนื่องจากความง่ายในการเรียนรู้ และความสะดวกในการทดสอบโปรแกรม เนื่องจาก Python เป็นภาษาประเภท Script ซึ่งจะแตกต่างกับภาษาประเภท Java หรือ C ที่ต้อง compile code ให้ออกมาเป็น binary ก่อนนำไปรันได้จริง เช่น หากต้องการทดสอบ function substring ว่าจะสามารถตัดคำให้เราถูกต้องหรือไม่ กรณีใช้ภาษา Java หรือ C ก็ต้องเขียน class, main function หรืออื่นๆ อีกมากมายกว่าจะเริ่มทดสอบ function เล็กๆ นี้ได้ แต่ใน Python นั้น เพียงแค่เข้า Python console ก็สามารถทดสอบ function เหล่านี้ได้ทันที

Django (อ่านว่าจังโก้ หรือแจงโก้ โดยไม่ออกเสียงตัว D) เป็น framework ที่ใช้ในการสร้าง Web Application ในฝั่งของ Back End ที่พัฒนาด้วยภาษา Python โดยในตัว framework จะมีส่วนประกอบทุกอย่างที่จำเป็นตั้งแต่การเชื่อมต่อฐานข้อมูล ไปจนถึงการ render ข้อมูลออกมาให้ฝั่ง Front End แสดงผลข้อมูลเหล่านั้นได้ ซึ่ง framework ในรูปแบบนี้ในภาษาอื่นๆ เช่น Ruby on rails สำหรับภาษา Ruby, Play Framework สำหรับภาษา Java หรือ Scala, Groovy on Grails สำหรับภาษา Groovy, Laravel สำหรับภาษา PHP, หรือ Express สำหรับภาษา Javascript ของ Node.js เป็นต้น ซึ่งข้อมูลที่อ้างอิงมาจาก www.hotframeworks.com จะเห็นว่า Django มีการใช้งานอย่างแพร่หลายมาก

1.การติดตั้ง Python และ Django
ติดตั้ง Python
- สำหรับ Windows สามารถ Download ได้จาก ที่นี่ ** สำคัญมากต้องติ๊กช่อง “Add python 3.X to PATH” ด้วย
- สำหรับ Linux version ใหม่ๆ จะมี python3 ติดตั้งมาให้ โดย default อยู่แล้ว
- สำหรับ Mac สามารถทำตาม Tutorial นี้ เพื่อติดตั้งได้
หลังจากติดตั้งแล้วบน Windows พิมพ์คำสั่ง $ py
บน Linux, Mac พิมพ์คำสั่ง $ python3
จะต้องได้หน้า python console ออกมาเหมือนในรูปด้านล่างนี้
2. ติดตั้ง pip3
pip3 คือ package manager ที่ใช้สำหรับติดตั้ง package เสริมให้กับ Python3 (คล้ายๆ คำสั่ง apt-get บน linux) โดยเราจะใช้ pip ในการติดตั้ง Django ต่อไป
- สำหรับ Windows คำสั่ง pip จะถูกติดตั้งมาอยู่แล้วบน python version 3.5 ขึ้นไป
- สำหรับ Linux ติดตั้งด้วยคำสั่ง $ sudo apt-get install python3-pip
- สำหรับ Mac ทำตาม Link ด้านบนเพื่อติดตั้ง pip3
เมื่อติดตั้งเสร็จสิ้นทดสอบด้วยการพิมพ์คำสั่ง $ pip3 ใน console
3. ติดตั้ง Django
พิมพ์คำสั่ง $ pip3 install django==1.11.5
แล้ว pip3 จะ download django เข้ามาติดตั้งในเครื่องให้โดยอัตโนมัติ
4. ตรวจสอบการติดตั้ง โดยพิมพ์คำสั่ง $ django-admin 

สร้าง Django Project
Browse ไปยัง Folder ที่ต้องการเก็บ project จากนั้น เริ่มสร้าง project ชื่อ “myapp” ด้วยคำสั่ง
$ django-admin startproject myapp
จะทำให้ได้โฟลเดอร์ myapp ซึ่งด้านในจะเก็บไฟล์ project ของ Django ดังนี้

1.manage.py คือไฟล์ script สำหรับรันคำสั่งต่างๆ ที่เกี่ยวข้องกับ Django โดยปกติไฟล์นี้จะไม่ถูกแก้ไขใด ๆ ทั้งสิ้น
2.__init__.py คือไฟล์ว่างๆ (ลองเปิดด้วย text editor ดูได้นะครับ) ไฟล์นี้มีไว้เพื่อให้ภาษา Python รู้ว่าโฟลเดอร์ที่อยู่นี้เป็นโฟลเดอร์ที่ใช้เก็บ Python Package โดยปกติไฟล์นี้จะถูกปล่อยเป็นไฟล์ว่าง ๆ ไว้แต่เราสามารถใส่ Python script เข้าไปได้เช่นกันแต่จะไม่ขอพูดถึงรายละเอียดในส่วนนี้ในบทความนี้ โดยรายละเอียดเพิ่มเติมของไฟล์นี้สามารถศึกษาได้จาก ที่นี่
3.settings.py คือไฟล์ที่ใช้เก็บ configuration ทั้งหมดของ project เอาไว้ เช่น การตั้งค่า Database, Timezone, Logging เป็นต้น ซึ่งค่าที่เก็บในนี้จะอยู่ในรูปแบบ key — value ซึ่งไฟล์นี้จะเป็นไฟล์แรกที่ Django เข้ามาอ่านเมื่อเริ่มการทำงานของ web server
4.urls.py คือไฟล์ที่ใช้เก็บการ routing ของ HTTP request ซึ่งจะกล่าวถึงในหัวข้อถัดไป
5.wsgi.py คือไฟล์ที่ใช้เก็บข้อมูลของ Django project ของเรา ใช้สำหรับการ deploy project เมื่อต้องการเชื่อมต่อกับ Web Server

ทดลองรัน Django Project ที่ port 8000 ด้วยคำสั่ง
$ py manage.py runserver 0.0.0.0:8000
หรือ สำหรับ Linux ให้รันคำสั่ง
$ python3 manage.py runserver 0.0.0.0:8000

