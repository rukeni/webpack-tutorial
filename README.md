# Webpack이 무엇인가요?

## 설명

> 웹팩의 핵심은 현대의 자바스크립트 응용 프로그램을 위한 정적 모듈 번들러이다.
> 웹팩은 애플리케이션을 처리할 때 하나 이상의 진입점에서 내부적으로 종속성 그래프를 만든 다음 프로젝트에 필요한 모든 모듈을 하나 이상의 번들로 결합합니다. 번들은 컨텐츠를 제공하는 정적 자산이다.

> ↑ 위설명은 웹팩 공식문서 설명입니다. [웹팩 사이트 링크](https://webpack.js.org/concepts/)
> 영어로 bundle은 꾸러미 묶음이라는 뜻입니다. 웹팩은 뭔가를 묶어버리는 역할 즉, 이삿짐 싸는게 다입니다.

하지만 이삿짐 싼다는 이 특성때문에 다양한 용도로 사용됩니다. 이번주는 같이 그부분을 알아볼 겁니다.

## Chapter 1. Entry와 Output

웹팩의 핵심인 엔트리 포인트와 아웃풋을 사용해보면서 맥락을 이해하겠습니다.
실습 : [[ch1]]

## Chapter 2. Loader와 Plugin

### Loader

Loader는 웹팩에서 다양한 유형의 파일을 처리하기 위한 전처리 도구입니다.(이미지, svg, css등)
로더를 사용하면 웹팩의 흐름은 다음과 같습니다.

1. 엔트리 파일 설정
2. 엔트리 파일이 가진 의존성을 체크
3. 의존성에 js가 아닌게 있다(원래라면 에러 발생)
4. 해당 의존성을 변환할 수 있는 로더가 있는지 체크한다.
5. 로더의 변환로직을 거친다.
6. 변환된 의존성과 함께 아웃풋 출력

이과정을 웹팩 공식문서는 이렇게 표현합니다.
> "이봐 webpack 컴파일러, require ()/import 문 내에서 '.확장자' 파일로 확인되는 경로를 발견하면 번들에 추가하기 전에 확장자-loader를 사용하여 변환해."

### Plugin

Plugin은 웹팩의 **라이프사이클관점**에서 개입이 필요할때 사용합니다.
대표적으로 HtmlWebpackPlugin이 있고 webpack의 결과물 script태그에 넣어서 을 html파일을 생성해주는 것입니다.

실습 : [[ch2]]

## 최적화 도구들

- [webpack-chart](https://alexkuz.github.io/webpack-chart/)
- [webpack-visualizer](https://chrisbateman.github.io/webpack-visualizer/)
- [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer)
- [webpack-bundle-optimizer helper](https://webpack.jakoblind.no/optimize/)
- [bundle-stats](https://github.com/relative-ci/bundle-stats)
