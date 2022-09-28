# Intellij tips

이 주제는 개발자로서 조금이라도 생산성을 높힐 수 있는 방법이 무엇이 있을까? 라는 생각에서 시작하게 되었습니다.



## Live Templates

개발자들은 반복적인 작업을 싫어합니다. 우리가 자주 사용하거나 작성하기 복잡한 내용을 템플릿화하여

좀 더 간편하고, 좀 더 빠르게 사용할 수 있다면 어떨까요? Intellij 에는  Live Templates이라는 편리한 기능이 있습니다

Live Templates이란 '약어'를 통해 사전에 정의된 code temaplate을 사용할 수 있는 기능입니다



### 다양한 Live Templates 소개

- psvm : public static void main

  - ![스크린샷 2022-09-25 오전 2.13.44](Images/psvf.png)

  - ![psvf2](Images/psvf2.png)

​				psvm을 타이핑 후 탭 혹은 엔터를 누르게 되면 약속된 템플릿이 자동으로 완성됩니다



- fori : iterlation loop 생성
- iter : iterable 또는 array iterate
  - ![fori_iter](Images/fori_iter.png)




- sout : System.out.println()
- soutm : 현재 클래스와 메서드 이름을 출력
- soutv : 선택한 변수를 출력
  - ![sout_soutm_soutv](Images/sout_soutm_soutv.png)





- ifn : if null
- inn : if not null
  - ![ifn_inn](Images/ifn_inn.png)




- 더 많은 templates : control + J 단축키를 누르게 되면 더 다양한 templates을 확인할 수 있습니다
  - ![control_j](Images/control_j.png)



-----------------

### Custom Live Template 만들기(1)



- Settings - Editor - Live Templates 

  ![live_templates_preference](Images/live_templates_preference.png)

​	지금까지 확인할 수 있었던 template들이 group 별로 존재하는 것을 확인할 수 있습니다

​	C, JAVA, HTTP Request, MAVEN, SQL .. 다양한 group이 존재합니다



- 우측에 Add 버튼을 클릭!
  ![add_live_templates](Images/add_live_templates.png)

​	JAVA  group에 새로운 template을 만들어 보도록 하겠습니다

​	template 추가는 오른쪽에 + 버튼을 눌러서 할 수 있습니다



- Custom Live Template 생성

  ![crate_live_templates](Images/crate_live_templates.png)

  - Abbreviation :  template 약어
  - Description : template 설명
  - Template text
    - METHOD_NAME : 메서드 이름
    - ARGS : arguments
    - END : template을 추가했을 때 커서가 오는 위치
    - 변수는 $로 감싸주어야 함



- Edit Variables

  ![create_live_templates_edit_variables](Images/create_live_templates_edit_variables.png)

​		default vaule에 기본 메서드 명을 설정해줄 수 있습니다



- 사용할 곳 정의 : Java - Declaration

  <img src="Images/create_live_templates_group.png" alt="create_live_templates_context" style="zoom:67%;" />

JAVA group에 Declaration을 선택해주고 apply를 눌러주면 완료!



- custom live template 확인![custom_live_template_prvm](Images/custom_live_template_prvm.png)


  ![create_prvm](Images/create_prvm.png)

위에서 설정한 prvm template 약어와 기본으로 설정된 메서드 이름을 확인할 수 있습니다

--------



### Custom Live Template 만들기(2)

더 나아가서 junit test에서도 활용해보도록 하겠습니다

- 가장 먼저 test용 코드를 작성하고, template으로 작성할 부분을 드래그 합니다
  ![junit_tdd_temaplte](Images/junit_tdd_temaplte.png)



- 이후 Code - Save as Live Template 을 눌러줍니다
  ![create_junit_tdd_template](Images/create_junit_tdd_template.png)
  - Abbrevation
  - Dscription
  - DISPLAY_NAME
  - METHOD_NAME
  - BODY
  - 사용할 곳 설정



- Edit Template Variables
  ![create_jun it_tdd_template_edit_variables](Images/create_junit_tdd_template_edit_variables.png)
  - DISPLAY_NAME : default value로 "Display name for my test" 작성
  - METHOD_NAME : Expression에 camelCase() 함수 사용, 파라미터로 DISPLAY_NAME을 전달
  - BODY : Assertion.fail 메서드 작성

​		

- 생성된 live template  확인
  ![create_junit_tdd](Images/create_junit_tdd.png)

METHOD_NAME에 DISPLAY_NAME을 camel case로 전달해주었기 때문에, 

custom live template을 생성하고 DisplayName을 수정해주면 메서드 이름도 같이 변경됩니다

-----------





## Postfix Completion

Postfix Completion은 .(dot) 뒤에 오는 접미사을 통해 기존에 정의된 표현식으로 변환할 수 있는 기능입니다.

코드를 작성하다가 커서가 다시 앞으로 가지 않아도 되어서 편리(?)한 것이 장점이라고 합니다

- var : "PostFix"에 해당하는 변수를 생성
  - before
    ![postfix_var](Images/postfix_var_before.png)
  - after
    ![postfix_var_after](Images/postfix_var_after.png)



- for

  <img src="Images/postfix_for.png" alt="postfix_for" style="zoom:67%;" />



- new
  <img src="Images/postfix_new.png" alt="postfix_new" style="zoom: 50%;" />



- nn
  <img src="Images/postfix_nn.png" alt="postfix_nn" style="zoom: 50%;" />



- opt
  <img src="Images/postfix_opt.png" alt="postfix_opt" style="zoom:50%;" />



- try
  <img src="Images/postfix_try.png" alt="postfix_try" style="zoom: 50%;" />



- 더 많은 postfix 목록
  <img src="Images/postfix_list.png" alt="postfix_list" style="zoom: 50%;" />



--------------



## Navigation in Intellij



### Find Recent Files

- 최근에 열어보거나 수정한 파일들의 목록을 확인할 수 있습니다
- split right : 해당 파일을 shift + enter 로 열게 되면 오른쪽에 분할되어 창이 열립니다
- back space 또는 delete를 누르면 목록에서 파일이 삭제됩니다

![find_recent_files](Images/find_recent_files.png)

- Recent Files 목록에서 검색
  ![find_recent_files_search](Images/find_recent_files_search.png)

### Recent Locations

- 최근에 열어보거나 수정한 파일들의 디테일한 코드 및 위치를 확인할 수 있습니다
- back space 또는 delete를 누르면 목록에서 파일이 삭제됩니다

![recent_locations](Images/recent_locations.png)

- Recent Locations 목록에서 수정된 부분만 보기

  ![recent_locations_chaged](Images/recent_locations_chaged.png)

- Recent Locations 목록에서 검색
  ![recent_locations_search](Images/recent_locations_search.png)

### Bookmarks

- bookmark 추가

  - anonymous bookmark : F11

    - 식별자가 없으며 원하는 만큼 추가 가능

  - mnemonic bookmark : Ctrl + F11

    - 니모닉 북마크는 숫자(0~9) 또는 문자 (A~Z)로 책갈피 추가 가능

    <img src="Images/mnemonic_bookmark.png" alt="mnemonic_bookmark" style="zoom:67%;" />

  

- bookmark 리스트 : Alt + 2

  ![bookmarks](Images/bookmarks.png)




- bookmark popup : Shift + F11
  ![bookmark_popup](Images/bookmark_popup.png)











































