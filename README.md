# sample swiftLint
[SwiftLint](https://github.com/realm/SwiftLint/blob/master/README_KR.md) 사용하면 좋습니다. 
- GitHub's Swift Style Guide 기반으로 코드 스타일과 규칙을 적용하는 라이브러리입니다. 

## 왜? 사용하면 좋나요?
- 기본적으로 Apple의 Swift 코드 스타일에서 벗어나면 빌드시 문제점이 있다고 알려주게 할 수 있습니다.(Rules, Opt-In Rules)
- 코드 스타일을 필요한 부분만 규칙에 벗어나면 문제가 있다고 커스텀이 가능합니다.(Defining Custom Rules)
- 자동으로 간격조정과 같은 일치하기 힘든 코드 부분을 빌드시 자동으로 맞춰주게 할 수 있습니다. (Auto-correct)

## 불편한 부분은 무엇인가요?
- swiftLint를 써본적이 없다면 불편합니다. 학습이 필요합니다. 
- 여러 개발자가 함께 협업해서 개발을 한다면, 이런 룰에 의해 빌드가 된다는 것을 사전에 합의해야됩니다.
- 빌드시 자동으로 수정이 되도록 적용시 의도한 시점에 코드 수정이 되지 않고, 코드들이 수정이 되서 형상관리 사용시 부주의 하게 되면, 코드 충돌이나 의도하지 않은 코드들이 반영되서 협업 개발시 문제가 될 소지가 있습니다. 


## 기본 사용방법
- 우선 룰에 대해 알아봅시다.

### 1. 룰
아래의 링크를 클릭해서 들어가면 현재까지의 룰 정보를 가져올 수 있습니다. 
- 링크 : https://github.com/realm/SwiftLint/tree/master/Source/SwiftLintFramework/Rules
들어가 보시면 다양한 룰들이 있습니다.

예를 들어 Rules 폴더 안에 들어가보면, 경로: [/ConditionalReturnsOnNewlineRule.swift](https://github.com/realm/SwiftLint/blob/master/Source/SwiftLintFramework/Rules/ConditionalReturnsOnNewlineRule.swift) 의 swift파일이 있습니다.

우리가 yaml 파일(swiftlint.yml)에서 사용을 한다면 <br />
해당 스위프트 파일을 스네이크 표기법으로 사용하면됩니다.
> 더 정확히는 룰 파일에 들어가서 identifier 를 확인합니다.
```
enabled_rules:
  - conditional_returns_on_newline

... (중략) ...

```
이렇게 하나하나 만들어진 룰들을 확인해서 적용해보며 테스트 해보면 됩니다. 
개별 룰 들에 대한 테스트 한 것들에 대한 설명은 아래에 하나씩 작성해나갈 것입니다. 


## 자동수정 사용방법
> 사용은 간단합니다. 기존 swiftlint에 autocorrect만 추가해서 실행하면됩니다.
- 설정한 경로가 없다면, 기본 경로의 .swiftlint.yml 가 실행되겠죠.

```
if which swiftlint >/dev/null; then
	swiftlint autocorrect
else
    echo "warning: SwiftLint not installed, download from https://github.com/realm/SwiftLint"
fi
```

or 

```
	swiftlint autocorrect --path 지정파일경로 
```


### autocorrect는 왜 사용하나요?
빌드시 자동으로 코드가 수정 됩니다. 여러 사람이 작업을 해서 올려도, 빌드만 하고 레파지토리에 반영한다면 공통된 스타일 가지게 된 상태로 소스 관리가 될 수 있죠.

- 언제하지


## 커스텀 사용방법
- 언제하지

## 셈플링
- 언제하지? 
