import java.util.*;

class Student {
    private int id;
    private String fname;
    private double cgpa;

    public Student(int id, String fname, double cgpa) {
        this.id = id;
        this.fname = fname;
        this.cgpa = cgpa;
    }

    public int getId() {
        return id;
    }

    public String getFname() {
        return fname;
    }

    public double getCgpa() {
        return cgpa;
    }
}

public class Solution {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);

        int testCases = Integer.parseInt(in.nextLine());
        List<Student> studentList = new ArrayList<>();

        while (testCases-- > 0) {
            int id = in.nextInt();
            String fname = in.next();
            double cgpa = in.nextDouble();

            studentList.add(new Student(id, fname, cgpa));
        }

        Collections.sort(studentList, (s1, s2) -> {
            if (Double.compare(s2.getCgpa(), s1.getCgpa()) != 0) {
                return Double.compare(s2.getCgpa(), s1.getCgpa()); // Descending CGPA
            }
            if (!s1.getFname().equals(s2.getFname())) {
                return s1.getFname().compareTo(s2.getFname()); // Ascending Name
            }
            return Integer.compare(s1.getId(), s2.getId()); // Ascending ID
        });

        for (Student student : studentList) {
            System.out.println(student.getFname());
        }

        in.close();
    }
}




output:



<img width="587" height="416" alt="image" src="https://github.com/user-attachments/assets/f5716d9b-b4a3-4c50-a4f8-587e516c58dc" />
