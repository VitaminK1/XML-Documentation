### 아비스 네트워크 XML 문서

XML은 맵 특정 기능을 정의하는데 사용됩니다.
_이 페이지는 GitHub Pages를 사용하여 호스팅되고 있습니다_

#### Editing Notes

1. Pages are formated in markdown and may contain HTML, HTML should only be used where absolutely needed.
2. Markdown is parsed with [kramdown](https://kramdown.gettalong.org/) which has an [enhanced syntax](https://kramdown.gettalong.org/syntax.html).
3. Care should be taken when removing trailing whitespace since markdown uses two spaces to create a newline.


#### Pull Requests

Pull requests should have the following things:

1. The commits should have a descriptive message and which is not in the past tense.

   For example:  
   `Describe the XYZ module with more detail.` or `Add detailed description for XYZ.` is good, but: `Added XYZ.` isn't.

2. Content should be grammatically correct and the spelling should be US English, e.g. Color not Colour.


#### 변경 사항 미리보기

1. 루비를 설치합니다. ([Mac](https://gorails.com/setup/osx/10.11-el-capitan), Windows, [Ubuntu](https://gorails.com/setup/ubuntu/15.10)) (레일즈는 필요하지 않습니다)
2. [bundler](http://bundler.io) 젬을 설치합니다.
2. 프로젝트 root디렉토리에서 `bundle install`을 실행합니다.
3. `bundle exec jekyll serve` 이나 `jekyll serve`을 실행합니다.
4. 브라우저에서 `localhost:4000`으로 접속합니다.
