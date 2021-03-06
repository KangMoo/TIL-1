# Javascript - chapter 07 생성자 함수



## 7.1 생성자 함수 개요

* 생성자 함수에서 객체 생성 : 생성자 함수는  `new` 키워드로 객체를 생성한다.

```html
var 객체or인스턴스 = new 생성자함수()
```

* `instanceof`키워드 : 해당 객체가 어떠한 생성자 함수로 생성되었는지 확인할 때 사용하는 키워드

#### 코드 7-4 메서드 생성

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <script type="text/javascript">
      function Student(name, kor, eng, mat, sci){
        this.이름 = name;
        this.국어 = kor;
        this.영어 = eng;
        this.수학 = mat;
        this.과학 = sci;

        this.sum = function(){
          return this.국어 + this.영어 + this.수학 + this.과학;
        };
        this.avg = function(){
          return this.sum()/4;
        };
      }

      let student1 = new Student ('김', 100, 90, 80, 70);
      let student2 = new Student ('이', 90, 85, 100, 60);
      console.log(student1.sum() + "/" + student1.avg());
      console.log(student2.sum() + "/" + student2.avg());

    </script>
  </head>
  <body>

  </body>
</html>

```

#### 결과 - 코드 7-4 메서드 생성

![1  메서드 생성 결과](https://user-images.githubusercontent.com/55272324/73228812-2691ca80-41bb-11ea-996d-d1a17cf854be.PNG)

## 7.2 프로토타입

* 프로토타입 : 생성자 함수로 생성된 객체가 공통으로 가지는 공간

#### 코드 7-8 : 프로토타입으로 메서드 생성

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <script type="text/javascript">
      function Student(name, kor, mat, eng, sci){
        this.이름 = name;
        this.국어 = kor;
        this.영어 = eng;
        this.수학 = mat;
        this.과학 = sci;
      }
      Student.prototype.getSum = function (){};
      Student.prototype.getAverage = function (){};
      Student.prototype.toString = function (){};
      }
    </script>
  </head>
  <body>

  </body>
</html>

```



## 7.3 new 키워드

* new 키워드를 사용하는 것과 사용하지 않는 것의 차이 : 일반적으로 this 키워드를 사용하면 window 객체를 나타낸다. 따라서 new 키워드를 사용하지 않으면, 함수를 실행하는 동안 window 객체에 속성을 추가한 것이 된다.

## 7.4 캡슐화

* 캡슐화 : 잘못 사용될 수 있는 객체의 특정 부분을 사용자가 사용할 수 없게 막는 기술이다.

#### 코드 7-13 캡슐화

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <script type="text/javascript">
      function Rectangle(w,h){
        let width = w;
        let height = h;
      }
      this.getWidth =function () { return width;};
      this.getHeight =function () { return height;};
      this.setWidth =function (w) {
        width = w;
      };

      this.setHeight =function (h){
        height = h;
      };
    </script>
  </head>
  <body>

  </body>
</html>

```



## 7.5 상속



## 7.6 조금 더 나아가기



