---
layout: post
title: 'Hello world test'
subtitle: 'this is subtitle'
author: 'LeeMinTaek'
header-style: text
tags:
  - jekyll
---

## 클래스 정의

ES6 에서 클래스를 정의하고 상속하는 방식은 이전 방식과는 다르게 매우 간결해졌다

아래와 같은 방식으로 클래스를 정의할 수 있다 contructor키워드를 이용해서 생성자 또한 정의해야한다.

```javascript
class HumanEs6 {
  constructor(name) {
    this.name = name;
  }
  sleep() {
    console.log('zzz');
  }
}
```

## 클래스 상속

이런 방식 이전에 클래스를 상속해주기 위해서는 이전 포스트에서도 서술했지만 여러가지 과정을 거쳐야 했다 그러나 class 키워드를 이용하면 아래와 같이 간단해진다.

```javascript
class HumanEs6 {
  constructor(name) {
    this.name = name;
  }
  sleep() {
    console.log('zzz');
  }
}

class StudentEs6 extends HumanEs6 {
  constructor(name, age) {
    super(name);
    this.age = age;
  }
  sleep() {
    super.sleep();
    console.log('학생은 잠자는 중입니다.');
  }

  learn() {
    console.log(this.name + '은 배우는 중입니다.');
  }
}
```

## 생성자 정의

상속받은 클래스의 생성자를 정의하기 위해서는 매개변수를 추가해 주고 자식 클래스의 속성을 정의하기 전에 부모 클래스의 생성자를 super키워드를 이용해서 호출해줘야 한다.

만약 자식 클래스의 생성자와 부모 클래스의 생성자가 변경사항이 없다면 생략해도 된다

```javascript
class StudentEs6 extends HumanEs6 {
  constructor(name, age) {
    super(name);
    this.age = age;
  }
}
```

## super키워드

자식클래스에서 부모클래스의 메소드를 사용하기 위해서 이전에는 부모의 프로토 타입에서 조회하는 형식으로 메소드를 조회했었다 내부적인 방식은 똑같지만 es6 버전에서는 좀더 간결해 졌다 바로 super키워드를 이용하면 되기 때문이다

```javascript
class StudentEs6 extends HumanEs6 {
  sleep() {
    super.sleep(); // 이와 같은 방식으로 간단하게 조회가 가능하다
    console.log('학생은 잠자는 중입니다.');
  }

  learn() {
    console.log(this.name + '은 배우는 중입니다.');
  }
}
```
