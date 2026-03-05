# Main
```java
public class Main
{
    public static void main(String[] args)
    {
        Book lotr = new Book();

        lotr.setTitle("The Hobbit");
        lotr.setAuthor("J. R. R. Tolkien");
        lotr.setPublisher("George Allen & Unwin");
        lotr.setPublicationDate("21 September 1937");

        lotr.printInfo();

        Encyclopedia TIETU = new Encyclopedia();

        TIETU.setTitle("The Illustrated Encyclopedia of the Universe");
        TIETU.setAuthor("Ian Ridpath");
        TIETU.setPublisher("Watson-Guptill");
        TIETU.setPublicationDate("2001");
        TIETU.setEdition("2nd");
        TIETU.setPages(384);

        TIETU.printInfo();
    }
}
```
# Book
```java
public class Book
{
    private String title, author, publisher, publicationDate;

    void setTitle(String title)
    {
        this.title = title;
    }
    void setAuthor(String author)
    {
        this.author = author;
    }
    void setPublisher(String publisher)
    {
        this.publisher = publisher;
    }
    void setPublicationDate(String publicationDate)
    {
        this.publicationDate = publicationDate;
    }
    String getTitle()
    {
        return title;
    }
    String getAuthor()
    {
        return author;
    }
    String getPublisher()
    {
        return publisher;
    }
    String getPublicationDate()
    {
        return publicationDate;
    }
    void printInfo()
    {
        System.out.println("Book Information: \n\t" + "Book Title: " + title + "\n\tAuthor: " + author + "\n\tPublisher: " + publisher + " \n\tPublication Date: " + publicationDate);
    }
}
```
# Encyclopedia
```java
public class Encyclopedia extends Book
{
    private String edition;
    private int pages;

    void setEdition(String edition)
    {
        this.edition = edition;
    }
    void setPages(int pages)
    {
        this.pages = pages;
    }
    String getEdition()
    {
        return edition;
    }
    int getPages()
    {
        return pages;
    }
    void printInfo()
    {
        super.printInfo();
        System.out.println("\tEdition: " + edition + "\n\tNumber of Pages: " + pages);
    }
}
```
