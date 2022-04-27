# Loader

가장 이해하기 쉽게 raw-loader라는게 어떻게 돌아가는지 보면 쉽습니다.
링크 : [raw-loader](https://github.com/webpack-contrib/raw-loader/blob/master/src/index.js)

1. 엔트리 포인트 파일을 읽는다(*.js)
2. 엔트리 포인트 파일의 의존성을 살핀다(import된 것들)
3. 그 중 js가 아닌 확장자는 loader가 작동한다.
4. 로더는 각기 식별할 파일확장자를 특정한다.
5. 로더에 의해 변환된 결과물을 포함하여 output을 만들어낸다.
6. 만일 해당 확장자를 담당할 로더가 없다면 웹팩은 에러를 뱉는다.