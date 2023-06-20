# exception
public class Stu { private int id; private String name; 
public Stu(int id, String name) { this.id = id; this.name = name;     
}

public static Stu find(int id) throws StuException { 
if (id == 123) {
return new Stu(123, "Çetin");
} 
else { throw new StuException("Öğrenci Bulunamadı");       
}
    }

public int getId() { return id;     }

public void setId(int id) { this.id = id;     }

public String getName() { return name;     }

public void setName(String name) { this.name = name;     }
}

public class StuException extends Exception {
    public StuException(String msg) {
        super(msg);
    }
}

public class Main {
    public static void main(String[] args) {

        Stu s = null;
        try {
            s = Stu.find(22);
            System.out.println("ID : " + s.getId());
            System.out.println("Name : " + s.getName());
        } catch (StuException e) {
            System.out.println(e.getMessage());
        }

    }
}


public class Person { private int age; 
public void setAge(int age) 
throws IllegalArgumentException { 	
if (age < 0) 		
{
throw new IllegalArgumentException("Yaş sıfırdan küçük olamaz!"); 		
}

this.age = age; 	}
}
