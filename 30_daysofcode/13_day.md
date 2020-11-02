# Problem 13/30

## Quiz : "Abstract Class"
객체지향, 추상클래스

## Solution !!
```
from abc import ABCMeta, abstractmethod    ### 추상클래스 모듈 불러오기

class Book(object, metaclass=ABCMeta):     ### 추상클래스 설정
    def __init__(self, title, author):     ### 생성자 함수 설정
        self.title=title
        self.author=author

    ### display() 함수 선언, 추상클래스 함수는 비어있는 함수여야 한다. 호출안됨.
    @abstractmethod
    def display(): pass

#Write MyBook class
class MyBook(Book) :                        ### Book 추상 클래스 상속
    def __init__(self, title, author, price) :   ### 생성자 함수 설정
        self.title = title
        self.author = author
        self.price = price

    ### 추상클래스에서 지정해 놓은 함수를 반드시 구현해야 한다.
    def display(self) :
        print("Title:", self.title)
        print("Author:", self.author)
        print("Price:", self.price)
```

