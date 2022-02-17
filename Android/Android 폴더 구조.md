# Android 폴더 구조

# ***Summary***

1. 모든 안드로이드 프로젝트는 MainActivity를 기본적으로 갖고 있어야 하며 manifests/AndroidManifest.xml에서 설정해준다.

2. 새로운 화면을 만들 때마다 Activity파일(.java파일)과 XML파일(xxxx.xml)을 쌍으로 만들어주고 Activity파일에서 XML파일을 연결해준다.

<aside>
➕ xml 파일은 UI를 구현한 파일

</aside>

# Detail

## app : 프로젝트 설정 패키지

### manifests : 앱의 전체적인 지도 역할

프로젝트를 빌드하기 위해 반드시 선행되어야 하는 필수 설정 요소

- AndroidManifest.xml : 안드로이드의 컨트롤 타워
    
    안드로이드 프로젝트는 "application"위에 "activity"가 실행되는 구조
    
    ex) XML버전, 인코딩 방법, Android 속성
    

### java : 프로그래밍 구현 부분

클래스를 관리하는 폴더

- MainActivity
    
    어플리케이션이 실행될 때 가장 먼저 실행되는 Activity
    
- onCreate()
- setContentView(R.layout.activity_main)
    - 에뮬레이터를 작동하면, 여기 적힌 파일을 실행시켜 에뮬레이터로 나타냄
    - layout 패키지 아래에 있는 activity_main.xml 파일을 View로 연결

### res : UI와 관련된 각종 리소스가 담기는 폴더

- **디자인의 뼈대**
    - layout : 각종 xml 파일
    
- **부수적인 저장소**
    - drawable : 이미지 파일 저장 패키지
    - mipmap : launcher 이미지(앱 아이콘) 저장 패키지
    - values : 문자열, 색상값, 수치값, 스타일 저장 패키지
        
        앱의 테마, 자주 사용되는 컬러 코드
        
        자주 사용하는 컬러에 특별한 명칭을 부여 후 사용 시마다 변수로 불러오고 싶다면 이 패키지에 저장 
        

## Gradle Scripts : 컴파일을 도와주는 패키지

- 어플리케이션을 빌드하기 위해 필요한 설정 옵션, 라이브러리 정보
- 자바나 코틀린으로 작성한 언어를 컴파일할 수 있도록 도와주는 역할
- 개발자가 직접 건드리는 경우는 많이 없음

<aside>
💡 **Project**

여러 프로젝트를 모아놓은 큰 범위

Project에 정의한 부분은 모든 프로젝트에 영향을 미침.

</aside>

<aside>
💡 **Module**

여러 프로젝트들 중 개별 프로젝트 단위

해당 모듈에만 영향을 미침.

</aside>

# etc

- (generated)라고 붗여진 폴더는 안드로이드 스튜디오에서 프로젝트 생성 시 자동으로 형성되는 폴더로, 개발자가 직접 다루는 일은 거의 없음
- (androidTest), (Test) 자동 생성된 폴더이며 테스트 코드를 작성할 때 사용되는 폴더

[참고 블로그](https://codeasy.tistory.com/6)