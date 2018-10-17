> สำหรับผู้อ่านทางบ้าน: บทนี้ครอบคลุมวิดีโอในส่วนของ [การติดตั้ง Python และ Code Editer](https://www.youtube.com/watch?v=pVTaqzKZCdA)
> 
> ในส่วนของบทนี้ อ้างอิงมาจากบทเรียนของ Geek Girls Carrots (https://github.com/ggcarrots/django-carrots)

Django ถูกเขียนโดยภาษา Python เพราะฉะนั้นเราจึงต้องใช้ Python ในการทำอะไรต่างๆใน Django งั้นเรามาเริ่มต้นด้วยการติดตั้ง Python กันเถอะ คุณต้องติดตั้ง Python เวอร์ชั่น 3.6 ถ้าหากคุณมีเวอร์ชั่นก่อนหน้านี้ คุณควรที่จะอัพเกรดมันก่อนนะ

<!--sec data-title="Install Python: Windows" data-id="python_windows" data-collapse=true ces-->

ขั้นตอนแรก คุณควรตรวจสอบว่าคอมพิวเตอร์ของคุณรัน Windows เวอร์ชั่น 32-bit หรือ 64-bit คุณสามารถตรวจสอบได้โดยการกดปุ่ม Windows และ ปุ่ม Pause/Break ซึ่งการกดปุ่มสองปุ่มนี้พร้อมกันคุณจะสามารถเปิดเข้าไปดูข้อมูลระบบของคุณได้ จากนั้นให้ดูที่ System type คุณสามารถดาวน์โหลด Python สำหรับ Windows ได้จากเว็บไซต์ https://www.python.org/downloads/release/python-343/ คลิกที่ลิงค์ Latest Python 3 Release - Python x.x.x ถ้าหากคอมพิวเตอร์ของคุณรัน Windows เวอร์ชั่น **64-bit** ให้ดาวน์โหลด **Windows x86-64 executable installer** ถ้าหากคอมพิวเตอร์ของคุณรัน Windows เวอร์ชั่นอื่น ให้ดาวน์โหลด **Windows x86 executable installer** หลังจากดาวน์โหลดไฟล์ *. msi มาแล้ว คุณควรเริ่มติดตั้ง (double-click ที่ไฟล์) และทำตามคำแนะนำของตัวติดตั้ง

สิ่งหนึ่งที่ต้องระวังก็คือ: ระหว่างการติดตั้ง คุณจะสังเกตเห็นหน้าต่างที่มีเครื่องหมาย "Setup" คุณควรตรวจสอบให้แน่ใจว่าคุณติ๊กที่ช่อง "Add Python 3.6 to PATH" และคลิกที่ "Install Now" ตามที่ปรากฏดังนี้:

![อย่าลืมเพิ่ม Python ไปยัง Path](../python_installation/images/python-installation-options.png)

When the installation completes, you may see a dialog box with a link you can follow to learn more about Python or about the version you installed. Close or cancel that dialog -- you'll be learning more in this tutorial!

In upcoming steps, you'll be using the Windows Command Line (which we'll also tell you about). For now, if you need to type in some commands, go to Start menu and enter "Command Prompt" into the search field there. (On older versions of Windows, you can start the Command Line with Start menu → Windows System → Command Prompt.) You can also hold in the Windows key and press the "R"-key until the "Run" window pops up. To open the Command Line, type "cmd" and press enter in the "Run" window.

![Type "cmd" in the "Run" window](../python_installation/images/windows-plus-r.png)

Note: if you are using an older version of Windows (7, Vista, or any older version) and the Python 3.6.x installer fails with an error, you can try either:

1. ติดตั้ง Windows Updates ทั้งหมด และลองติดตั้ง Python 3.6 อีกครั้ง; หรือ
2. ติดตั้ง [Python รุ่นเก่า](https://www.python.org/downloads/windows/) เช่น e.g., [3.4.6](https://www.python.org/downloads/release/python-346/)

If you install an older version of Python, the installation screen may look a bit different than shown above. Make sure you scroll down to see "Add python.exe to Path", then click the button on the left and pick "Will be installed on local hard drive":

![Add Python to the Path, older versions](../python_installation/images/add_python_to_windows_path.png)

<!--endsec-->

<!--sec data-title="Install Python: OS X" data-id="python_OSX"
data-collapse=true ces-->

> **หมายเหตุ** ก่อนที่คุณจะติดตั้ง Python บนระบบปฏิบัติการ OS X คุณควรตรวจสอบให้แน่ใจว่าการตั้งค่า Mac ของคุณนั้นอนุญาตให้ติดตั้งแพคเก็จที่ไม่ได้มาจาก App Store ได้ ให้ไปที่ System Preferences (มันอยู่ในโฟลเดอร์ Applications) คลิก "Security & Privacy," หลังจากนั้นให้คลิกที่แท็บ "General" ถ้าหาก "Allow apps downloaded from:" ถูกตั้งค่าให้อยู่ใน "Mac App Store," ให้เปลี่ยนเป็น "Mac App Store and identified developers."

You need to go to the website https://www.python.org/downloads/release/python-361/ and download the Python installer:

* ดาวน์โหลดไฟล์ *Mac OS X 64-bit/32-bit installer*
* Double click ที่ *python-3.4.3-macosx10.6.pkg* เพื่อรันตัวติดตั้ง

<!--endsec-->

<!--sec data-title="Install Python: Linux" data-id="python_linux"
data-collapse=true ces-->

It is very likely that you already have Python installed out of the box. To check if you have it installed (and which version it is), open a console and type the following command:

{% filename %}command-line{% endfilename %}

    $ python3 --version
    Python 3.6.1
    

If you have a different 'micro version' of Python installed, e.g. 3.6.0, then you don't have to upgrade. If you don't have Python installed, or if you want a different version, you can install it as follows:

<!--endsec-->

<!--sec data-title="Install Python: Debian or Ubuntu" data-id="python_debian" data-collapse=true ces-->

Type this command into your console:

{% filename %}command-line{% endfilename %}

    $ sudo apt install python3.6
    

<!--endsec-->

<!--sec data-title="Install Python: Fedora" data-id="python_fedora"
data-collapse=true ces-->

Use this command in your console:

{% filename %}command-line{% endfilename %}

    $ sudo dnf install python3
    

If you're on older Fedora versions you might get an error that the command `dnf` is not found. In that case, you need to use `yum` instead.

<!--endsec-->

<!--sec data-title="Install Python: openSUSE" data-id="python_openSUSE"
data-collapse=true ces-->

Use this command in your console:

{% filename %}command-line{% endfilename %}

    $ sudo zypper install python3
    

<!--endsec-->

Verify the installation was successful by opening a command prompt and running the `python3` command:

{% filename %}command-line{% endfilename %}

    $ python3 --version
    Python 3.6.1
    

**NOTE:** If you're on Windows and you get an error message that `python3` wasn't found, try using `python` (without the `3`) and check if it still might be a version of Python 3.6.

* * *

If you have any doubts, or if something went wrong and you have no idea what to do next, please ask your coach! Sometimes things don't go smoothly and it's better to ask for help from someone with more experience.