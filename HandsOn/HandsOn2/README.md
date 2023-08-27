# HandsOn2
![image](https://github.com/Abdelrhman-Sayed70/OOP/assets/99830416/65be2d49-9787-4138-951c-b8531645925d)
![image](https://github.com/Abdelrhman-Sayed70/OOP/assets/99830416/9984ba50-cdc6-40a5-9d1a-a100f1319142)

## Solution
```java
package mainpackage;

public class Book {
    private String name;
    private final int numberOfPages;
    private float price;

    public Book(int numberOfPages){
        this.numberOfPages = numberOfPages;
    }

    public Book(String name, int numberOfPages){
        this(numberOfPages); // constructor chaining
        this.name = name;
    }

    public Book(String name, int numberOfPages, float price){
        this(name, numberOfPages); // constructor chaining
        this.price = price;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getNumberOfPages() {
        return numberOfPages;
    }

    public float getPrice() {
        return price;
    }

    public void setPrice(float price) {
        this.price = price;
    }

    public void displayBookInfo(){
        System.out.println("Book name: " + this.name);
        System.out.println("Number of pages: " + this.numberOfPages);
        System.out.println("Price: " + this.price);
    }
}
```

```java
package mainpackage;

public class Author {
    private final String name;
    private Book []books;
    private int numberOfBooks = 3;

    public Author(String name){
        this.name = name;
        books = new Book[numberOfBooks];
    }

    public String getName() {
        return name;
    }

    public void addBook(Book book, int index){
        books[index] = book;
    }

    public Book searchBook(String name){
        for(Book book : books){
            if (book != null && book.getName().equals(name))
                return book;
        }
        return null;
    }

    public void displayBooksDate(){
        System.out.println("Displaying " + this.name + " author books date...");
        for(Book book: books){
            book.displayBookInfo();
        }
    }
}
```

```java
package mainpackage;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Author author = new Author("abdo");

        Book []books = new Book[3];
        books[0] = new Book(1);
        books[1] = new Book("The Days", 2);
        books[2] = new Book("Days2" , 3, 50.5f);

        books[0].setName("A");
        books[0].setPrice(100.0f);

        books[1].setPrice(200.0f);

        for(int i = 0; i < 3; i++) {
            author.addBook(books[i], i);
        }

        String bookName = "The Days";
        Book searchedBook = author.searchBook(bookName);
        if (searchedBook != null) {
            System.out.println("Book found, here is its data..");
            searchedBook.displayBookInfo();
        }

        System.out.println("Author all books data..");
        author.displayBooksDate();
    }
}
```
