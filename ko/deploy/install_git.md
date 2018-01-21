Git은 많은 프로그래머들이 사용하고 있는 "버전 제어 시스템(version control system)"이에요. 이 소프트웨어는 변경 내용을 추적할 수 있어 나중에 특정 버전을 다시 호출 할 수 있어요. 마이크로소프트 워드에 있는 "변경 내용 추적하기(track changes)"와 같은 기능이지만 이보다 훨씬 더 강력하죠.

## Git 설치하기

<!--sec data-title="Installing Git: Windows" data-id="git_install_windows"
data-collapse=true ces-->

Git은 [git-scm.com](https://git-scm.com/)에서 다운로드 할 수 있어요. You can hit "next" on all steps except for one; in the fifth step entitled "Adjusting your PATH environment", choose "Use Git and optional Unix tools from the Windows Command Prompt" (the bottom option). 나머지는 모두 기본 설정대로 해도 됩니다. 윈도우 스타일, 유닉스 스타일로 라인엔딩 커밋하기(commit Unix-style line endings) 를 체크하는 것도 좋습니다.

Do not forget to restart the command prompt or powershell after the installation finished successfully. <!--endsec-->

<!--sec data-title="Installing Git: OS X" data-id="git_install_OSX"
data-collapse=true ces-->

[git-scm.com](https://git-scm.com/)에서 맥용 설치파일을 다운받은 다음 실행해 나오는 지시사항에 따라 설치하시면 됩니다.

> **Note** If you are running OS X 10.6, 10.7, or 10.8, you will need to install the version of git from here: [Git installer for OS X Snow Leopard](https://sourceforge.net/projects/git-osx-installer/files/git-2.3.5-intel-universal-snow-leopard.dmg/download)

<!--endsec-->

<!--sec data-title="Installing Git: Debian or Ubuntu" data-id="git_install_debian_ubuntu"
data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

```bash
$ sudo apt-get install git
```

<!--endsec-->

<!--sec data-title="Installing Git: Fedora" data-id="git_install_fedora"
data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

```bash
$ sudo dnf install git
```

<!--endsec-->

<!--sec data-title="Installing Git: openSUSE" data-id="git_install_openSUSE"
data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

```bash
$ sudo zypper install git
```

<!--endsec-->