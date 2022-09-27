# Intellij와 친해지기



## Live Templates

이 주제는 개발자로서 조금이라도 생산성을 높힐 수 있는 방법이 무엇이 있을까? 라는 생각에서 시작하게 되었습니다.

개발자들은 반복적인 작업을 싫어합니다. 우리가 자주 사용하거나 작성하기 복잡한 내용을 템플릿화하여

좀 더 간편하고, 좀 더 빠르게 사용할 수 있다면 어떨까요? Intellij 에는  Live Templates이라는 편리한 기능이 있습니다



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





### Custom Live Template 만들기

![스크린샷 2022-09-25 오전 3.00.02](/Users/snow/Screenshots/스크린샷 2022-09-25 오전 3.00.02.png)

지금까지 확인할 수 있었던 template들이 group 별로 존재하는 것을 확인할 수 있습니다

C, JAVA, HTTP Request, MAVEN, SQL .. 다양한 group이 존재합니다



![스크린샷 2022-09-25 오전 3.00.02](/Users/snow/Screenshots/스크린샷 2022-09-25 오전 3.03.14.png)

JAVA  group에 새로운 template을 만들어 보도록 하겠습니다

template 추가는 오른쪽에 + 버튼을 눌러서 할 수 있습니다



![스크린샷 2022-09-25 오전 3.08.26](/Users/snow/Screenshots/스크린샷 2022-09-25 오전 3.08.26.png)

- Abbreviation :  template 약어

- Description : template 설명

- Template text

  - $METHOD_NAME$ : 메서드 이름
  - $ARGS$ : arguments
  - $END$ : template을 추가했을 때 커서가 오는 위치

  

<img src="/Users/snow/Screenshots/스크린샷 2022-09-25 오전 3.14.28.png" alt="스크린샷 2022-09-25 오전 3.14.28" style="zoom:50%;" />

JAVA group에 Declaration을 선택해주고 apply를 눌러주면 완료!



![스크린샷 2022-09-25 오전 3.32.24](/Users/snow/Screenshots/스크린샷 2022-09-25 오전 3.32.24.png)

![스크린샷 2022-09-25 오전 3.32.32](/Users/snow/Screenshots/스크린샷 2022-09-25 오전 3.32.32.png)

위에서 생성한 prvm 약어에 해당하는 template을 확인할 수 있습니다



더 나아가서 junit test에서도 활용해보도록 하겠습니다

![스크린샷 2022-09-25 오전 3.35.47](/Users/snow/Screenshots/스크린샷 2022-09-25 오전 3.35.47.png)

test용 template 코드를 작성하고, template으로 작성할 부분을 드래그 합니다

이후 Code메뉴 - Save as Live Template 을 눌러줍니다

![스크린샷 2022-09-25 오전 3.47.37](/Users/snow/Screenshots/스크린샷 2022-09-25 오전 3.47.37.png)

![스크린샷 2022-09-25 오전 3.50.31](/Users/snow/Screenshots/스크린샷 2022-09-25 오전 3.50.31.png)

- Edit Template Variables

  -  DISPLAY_NAME에  Default value 값으로 string  값을 넣어 줌
  - METHOD_NAME에 Expression에 camelCase(DISPLAY_NAME)을 넣어주어
    DISPLAY_NAME이 camel case로 METHOD_NAME이 됨
  - BODY에는 Assertions.fail 함수를 넣어 줌

  

![스크린샷 2022-09-25 오전 3.56.40](/Users/snow/Screenshots/스크린샷 2022-09-25 오전 3.56.40.png)

DISPLAY_NAME을 수정하면 METHOD_NAME도 같이 수정된다!





## Debugging Stream

