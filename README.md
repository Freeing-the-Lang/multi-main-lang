### 🧽 multi-main-lang → Spongelang → MultiMain-OS 연동 구조
multi-main-lang은 여러 개의 `main` 블록을 가질 수 있는 언어입니다.

이 언어는 스스로 실행하지 않으며,  
작성된 모든 main은 Spongelang에 의해 **의미 노드(MeaningNode)** 로 흡수됩니다.

Spongelang은 이러한 main들을 스폰지처럼 모두 받아들여  
하나의 MeaningGraph로 병합합니다.

그 후 MultiMain-OS가 이 그래프를 실행하여  
프로그램이 실제로 동작하게 됩니다.

즉 전체 실행 흐름은 다음과 같습니다:

multi-main-lang → Spongify (Spongelang) → MeaningGraph → MultiMain-OS Runtime

이 구조 덕분에 multi-main-lang은  
여러 main을 가진 프로그램을 자연스럽게 표현할 수 있습니다.


---



여러 개의 main()을 기본으로 가진 새로운 언어


Spongelang 의미 엔진 + MultiMain-OS 실행 플랫폼 기반


# 🧠 multi-main-lang
### A language that naturally supports multiple `main` blocks  
### Built on top of Spongelang (Meaning Engine) + MultiMain-OS (Execution Platform)

---

## 🌟 소개
**multi-main-lang**은 기존 언어의 전제를 완전히 벗어난 언어입니다.

일반 언어는 반드시 "main 함수가 하나" 있어야 실행이 되지만,  
multi-main-lang은 **여러 main을 동시에 포함하는 것을 기본 문법으로 허용**합니다.

이 언어는 Spongelang의 의미 기반 AST를 사용하며,  
MultiMain-OS 위에서 자연스럽게 실행됩니다.

즉:

- 여러 main을 작성할 수 있고  
- 순서는 직접 지정하거나  
- MultiMain-OS가 자동으로 결정합니다  

---

## ✨ 특징

### ✔ 여러 개의 main 지원



main First:
print "One"


main Second:
print "Two"


main Third:
print "Three"



각 main은 독립된 실행 노드가 되며,  
Spongelang Meaning Graph로 변환됩니다.

---

### ✔ 실행 순서 제어 방식 2가지 지원

1) **자동(기본)**  
MultiMain-OS가 Spongelang 의미 그래프를 분석해 실행 순서를 자동 생성.

2) **수동(옵션)**  
`User-can-designate-order` 모듈을 사용해 순서를 직접 지정.




mmain . --order order.mmo



---

### ✔ Spongelang 기반 의미(AST) 언어
multi-main-lang은 Spongelang의 "언어 같으면서 언어 아닌" 의미 모델을 그대로 확장한 형태.

- 문법 최소화  
- 의미 중심  
- main 블록은 MeaningNode로 변환  
- C 언어 제외 (전체 생태계 C 제외 정책)

---

### ✔ MultiMain-OS와 100% 연동
multi-main-lang은 단독으로도 의미 AST를 생성하지만,  
진짜 활용은 **MultiMain-OS 위에서 동작할 때 극대화**됩니다.

규칙:

- 각 main → Graph Node (MainNode)  
- 자동/수동 순서 결정  
- Meaning Runtime에서 실행  

---

## 📦 파일 확장자
기본 확장자는:




.mm



예:



hello.mm
logic.mm
render.mm



---

## ▶ 실행 예시

### 1) 코드 작성
hello.mm:



main Start:
print "Starting..."


main Work:
print "Working..."


main End:
print "Ending..."



### 2) 실행



mmain hello.mm



MultiMain-OS는 자동으로 의미 그래프를 구성하고  
여러 main을 순서에 맞게 실행합니다.

---

## 🧱 내부 구조



multi-main-lang
├── parser/
├── meaning/
├── emitter/
├── runtime/
└── examples/



multi-main-lang은 자체 문법을 갖고 있지만  
모든 실행은 Spongelang 의미 엔진을 통해 이루어집니다.

---

## 🚫 제한 (전체 생태계와 동일)
- C 언어(.c) 전부 제외  
- C main 지원 없음  
- C/C++ ABI 호환 불필요  
- 전처리 기반 언어 제외  

---

## 🔮 철학
- "main 하나"라는 제약은 낡은 개념이다  
- 프로그램은 여러 시작점이 있을 수 있다  
- 순서는 자동으로도, 수동으로도 결정할 수 있다  
- Spongelang은 언어를 흡수하고  
- MultiMain-OS는 실행을 담당하며  
- multi-main-lang은 그 언어적 표현이다  

---

## 📄 라이선스
MIT License

