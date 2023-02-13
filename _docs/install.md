---
title: Jekyll 설치
tags: 
 - jekyll
 - Ruby
description: Ruby 
---

# Jekyll 설치

[ Jekyll 공식 홈페이지](https://jekyllrb.com/ " Jekyll 공식 홈페이지")

- 설치 환경은 Ubuntu 20.04 LTS x64 입니다.

1.  Ruby 설치
```
sudo apt-get install ruby-full build-essential zlib1g-dev
```

2. bashrc파일에 rubyGem path를 지정해준다.  
```
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
```
3. 바뀐 .bashrc의 path 값을 적용한다
```
source ~/.bashrc
```
4. jekyll과 bundler설치
```
gem install jekyll bundler
```
버전에 따라 의존성 에러가 날 수 있다, 아래처럼
```
ERROR:  Error installing jekyll:
	The last version of sass-embedded (~> 1.54) to support your Ruby & RubyGems was 1.57.1. Try installing it with `gem install sass-embedded -v 1.57.1` and then running the current command again
	sass-embedded requires RubyGems version >= 3.3.22. The current RubyGems version is 3.1.2. Try 'gem update --system' to update RubyGems itself.
Successfully installed bundler-2.4.4
Parsing documentation for bundler-2.4.4
Done installing documentation for bundler after 0 seconds
1 gem installed
```

위와 같은 에러가 생길 경우 bundler , Jeykller 를 따로 설치 한다
```
gem install bundler
gem install jekyll --version="~> 4.2.0"
```

여기 까지 설치가 완료 되었습니다.

## Jekyll blog 만들기
```
jekyll new --skip-bundle .
```

#### _config.yml 를 수정할 경우
bundle install 를 꼭 실행 해 주어야 한다.
```
bundle install
```

##### Github Pages gem 업데이트
Bundler를 설치한 경우 bundle update github-pages를 실행합니다.

Bundler가 설치되어 있지 않으면 gem update github-pages를 실행합니다.
```
bundle update github-pages
//gem update github-pages
```

#### 로컬에서 블러그 수정사항을 확인하려면
```
bundle exec jekyll serve --livereload
```
