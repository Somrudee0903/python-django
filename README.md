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
Browse ไปยัง Folder ที่ต้องการเก็บ project จากนั้น เริ่มสร้าง project ชื่อ “my_library” (ห้องสมุดของฉัน) ด้วยคำสั่ง

$ django-admin startproject my_library

จะทำให้ได้โฟลเดอร์ my_library ซึ่งด้านในจะเก็บไฟล์ project ของ Django
