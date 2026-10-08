# Code

```java
class Book {

    int id;
    String title;
    String author;
    double price;
    static int count = 0;

    public Book(int id, String title, String author, double price) {
        this.id = id;
        this.title = title;
        this.author = author;
        this.price = price;
        count++;
    }

    public void display() {
        System.out.println("Book ID: " + id + " Title: " + title + " Author: " + author + " Price: $" + price);
    }

    public void search(int searchId) {
        if (this.id == searchId) {
            System.out.println("Match Found for ID: " + searchId + "\n");
            this.display();
        }
    }

    public void search(String searchTitle) {
        if (this.title.equals(searchTitle)) {
            System.out.println("Match Found for Title: " + searchTitle + "\n");
            this.display();
        }
    }

    public static Book costlier(Book b1, Book b2) {
        if (b1.price >= b2.price) {
            return b1;
        } else {
            return b2;
        }
    }
}

public class BookRun {
    public static void main(String[] args) {

        Book b1 = new Book(101, "Java Programming", "James Gosling", 49.99);
        Book b2 = new Book(102, "Clean Code", "Robert C. Martin", 35.50);
        Book b3 = new Book(103, "Effective Java", "Joshua Bloch", 55.00);

        System.out.println("Total books created: " + Book.count);

        b1.display();
        b2.display();
        b3.display();

        b1.search(102);
        b2.search(102);
        b3.search(102);

        b1.search("Java Programming");
        b2.search("Java Programming");
        b3.search("Java Programming");

        Book expensive = Book.costlier(b1, b3);
        System.out.println("The costlier book is:");
        expensive.display();
    }
}
```

# Output

```
Total books created: 3
Book ID: 101 Title: Java Programming Author: James Gosling Price: $49.99
Book ID: 102 Title: Clean Code Author: Robert C. Martin Price: $35.5
Book ID: 103 Title: Effective Java Author: Joshua Bloch Price: $55.0
Match Found for ID: 102

Book ID: 102 Title: Clean Code Author: Robert C. Martin Price: $35.5
Match Found for Title: Java Programming

Book ID: 101 Title: Java Programming Author: James Gosling Price: $49.99
The costlier book is:
Book ID: 103 Title: Effective Java Author: Joshua Bloch Price: $55.0
```
