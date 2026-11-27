# Modern Java Features – Coding Examples

## 1. var Keyword – Java 10

### Without var

```java
public class Main {
    public static void main(String[] args) {

        String name = "Raghu";
        int age = 26;
        double marks = 89.5;
        boolean isPassed = true;

        System.out.println(name);
        System.out.println(age);
        System.out.println(marks);
        System.out.println(isPassed);
    }
}
```

### With var

```java
public class Main {
    public static void main(String[] args) {

        var name = "Raghu";
        var age = 26;
        var marks = 89.5;
        var isPassed = true;

        System.out.println(name);
        System.out.println(age);
        System.out.println(marks);
        System.out.println(isPassed);
    }
}
```

## 2. Text Blocks – Java 15

### Without Text Blocks

```java
public class Main {
    public static void main(String[] args) {

        String json = "{\n" +
                      "    \"name\": \"Raghu\",\n" +
                      "    \"age\": 26,\n" +
                      "    \"course\": \"Java\"\n" +
                      "}";

        System.out.println(json);
    }
}
```

### With Text Blocks

```java
public class Main {
    public static void main(String[] args) {

        String json = """
                {
                    "name": "Raghu",
                    "age": 26,
                    "course": "Java"
                }
                """;

        System.out.println(json);
    }
}
```

### SQL Query – Without Text Blocks

```java
public class Main {
    public static void main(String[] args) {

        String query = "SELECT * FROM students " +
                       "WHERE marks > 80 " +
                       "ORDER BY marks DESC";

        System.out.println(query);
    }
}
```

### SQL Query – With Text Blocks

```java
public class Main {
    public static void main(String[] args) {

        String query = """
                SELECT *
                FROM students
                WHERE marks > 80
                ORDER BY marks DESC
                """;

        System.out.println(query);
    }
}
```

## 3. Switch Expressions – Java 14

### Without Switch Expressions

```java
public class Main {
    public static void main(String[] args) {

        int day = 2;
        String result;

        switch (day) {

            case 1:
                result = "Monday";
                break;

            case 2:
                result = "Tuesday";
                break;

            case 3:
                result = "Wednesday";
                break;

            default:
                result = "Invalid Day";
        }

        System.out.println(result);
    }
}
```

### With Switch Expressions

```java
public class Main {
    public static void main(String[] args) {

        int day = 2;

        String result = switch (day) {

            case 1 -> "Monday";
            case 2 -> "Tuesday";
            case 3 -> "Wednesday";
            default -> "Invalid Day";
        };

        System.out.println(result);
    }
}
```

### Student Grading – Without Switch Expressions

```java
public class Main {
    public static void main(String[] args) {

        int marks = 85;
        String grade;

        switch (marks / 10) {

            case 10:
            case 9:
                grade = "A Grade";
                break;

            case 8:
                grade = "B Grade";
                break;

            case 7:
                grade = "C Grade";
                break;

            case 6:
                grade = "D Grade";
                break;

            default:
                grade = "Fail";
        }

        System.out.println(grade);
    }
}
```

### Student Grading – With Switch Expressions

```java
public class Main {
    public static void main(String[] args) {

        int marks = 85;

        String grade = switch (marks / 10) {

            case 10, 9 -> "A Grade";
            case 8 -> "B Grade";
            case 7 -> "C Grade";
            case 6 -> "D Grade";
            default -> "Fail";
        };

        System.out.println(grade);
    }
}
```

### Switch Expression – Using yield

```java
public class Main {
    public static void main(String[] args) {

        int marks = 95;

        String grade = switch (marks / 10) {

            case 10, 9 -> {
                System.out.println("Excellent Performance");
                yield "A Grade";
            }

            case 8 -> {
                System.out.println("Good Performance");
                yield "B Grade";
            }

            default -> "Fail";
        };

        System.out.println(grade);
    }
}
```
