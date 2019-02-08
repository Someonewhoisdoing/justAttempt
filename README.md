import java.util.Arrays;

public class Lambdas {
    public static void main(String[] args) {

        String[] colors = {"green", "blue", "white", "yellow", "red"};

        Person p1 = new Person("Alex", 21);
        Person p2 = new Person("Tom", 32);
        Person p3 = new Person("John", 22);
        Person p4 = new Person("Jack", 35);

        Person[] persons = {p1, p2, p3, p4};

        // Arrays.sort(persons, new Comparator<Person>(){
        //     @Override
        //     public int compare(Person o1, Person o2){
        //         return o2.getAge() - o1.getAge();}
        //  });
        //  System.out.println(Arrays.toString(persons));


        Arrays.sort(persons, (v1, v2) -> {
            if (v2.getAge() - v1.getAge() != 0) {
                return v2.getAge() - v1.getAge();
            } else {
                return v2.getName().compareTo(v1.getName());
            }
        });
        System.out.println(Arrays.toString(persons));

        // Arrays.sort(colors, new Comparator<String>() {
        //    @Override
        //    public int compare(String s1, String s2) {
        //        return s1.charAt(s1.length() - 1) - s2.charAt(s2.length() - 1);}
        //});

        //  System.out.println(Arrays.toString(colors));


        Arrays.sort(colors, (s1, s2) -> {
            System.out.println("hello!");
            return s1.charAt(s1.length() - 1) - s2.charAt(s2.length() - 1);
        });

        System.out.println(Arrays.toString(colors));
    }

}

class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    public String toString() {
        return name + " " + age;
    }
}
