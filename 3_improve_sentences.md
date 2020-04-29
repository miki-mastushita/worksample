# selfについて
`self`は **オブジェクトそのもの** を指します。  
オブジェクトにはクラスとインスタンスがあるため、使う場所によって「 **クラスそのもの** 」「 **インスタンスそのもの** 」を指します。

  - インスタンスメソッド内ではインスタンスそのものを指す。
  - インスタンスメソッド内でも`self.class`という記述でクラスそのものを指す。
  - クラス内直下ではクラスそのものを指す。
  - クラスメソッド内ではクラスそのものを指す。  

 また、`self`を使うと下記のことができます。  
 1. インスタンスを指すことで、そのクラス内のインスタンスオブジェクトを呼び出す。  
 1. クラスを指すことで、クラスメソッドを定義する。  


<例> 
1. クラス内のインスタンスオブジェクトを呼び出す。  
   ```  
   class Human
    attr_accessor :name
     def initialize(name)
     self.name = name
    end
   end
   
   human = Human.new("taro")
   puts human.name  
   ```  
   実行結果  
   ```  
   taro
   ```  
   ここでは`self`でHumanクラス内のインスタンス`initialize(name)`を指しています。  
   `self.name = name`で引数nameを代入し、`human = Human.new("taro")`で変数"taro"を与えました。  
   そうすると`self`に代入された`name`の変数である"taro"が呼び出されます。
   
   
1. クラスメソッドを定義する。
   ```  
   class Foo
    def self.description
    puts "bar"
    end
   end
   ```
   ここでは `self`で`Foo`というクラス自身を指し、「`description`で`bar`を表示する」というクラスメソッドを定義しました。  
   定義したメソッドを呼び出す（`Foo.description`）と `bar`が表示されます。
      
