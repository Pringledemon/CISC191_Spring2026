# Main
```java
public class Main
{
    public static void main(String[] args)
    {
        course DSD1 = new course();

        DSD1.setCourseNumber("ECE287");
        DSD1.setCourseTitle("Digital Systems Design");

        DSD1.printInfo();

        Offeredcourse DSD2 = new Offeredcourse();

        DSD2.setCourseNumber("ECE287");
        DSD2.setCourseTitle("Digital Systems Design");
        DSD2.setInstructorName("Mark Patterson");
        DSD2.setLocation("Wilson Hall 231");
        DSD2.setClassTime("WF: 2-3:30 pm");

        DSD2.printinfo();
    }
}
```
# Course
```java
public class course
{
    private String courseNumber, courseTitle;

    void setCourseNumber(String courseNumber)
    {
        this.courseNumber = courseNumber;
    }
    void setCourseTitle(String courseTitle)
    {
        this.courseTitle = courseTitle;
    }
    String getCourseNumber()
    {
        return courseNumber;
    }
    String getCourseTitle()
    {
        return courseTitle;
    }
    void printInfo()
    {
        System.out.println("Course Information: \n\tCourse Number: " + courseNumber + "\n\tCourse Title: " + courseTitle);
    }
}
```
# OfferedCourse
```java
public class OfferedCourse extends course
{
    private String instructorName, location, classTime;

    void setInstructorName(String instructorName)
    {
        this.instructorName = instructorName;
    }
    void setLocation(String location)
    {
        this.location = location;
    }
    void setClassTime(String classTime)
    {
        this.classTime = classTime;
    }
    String getInstructorName()
    {
        return instructorName;
    }
    String getLocation()
    {
        return location;
    }
    String getClassTime()
    {
        return classTime;
    }
    void printinfo()
    {
        super.printInfo();
        System.out.println("\tInstructor Name: " + instructorName + "\n\tLocation: " + location + "\n\tClass Time: " + classTime);
    }
}
```
