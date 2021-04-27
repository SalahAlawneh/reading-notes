# Web App Security
- Hibernate ORM is `an object–relational mapping tool for the Java programming language. It provides a framework for mapping an object-oriented domain model to a relational database`=> From Wikipedia
- so hibernate will map the domaing into relational data base
- the way that we establish many to many relationship is not that different from one to many, but with:
   - additional annotation
   - third table to make the connection
- in this article the relation was between an empolye table and project table, and it's make sense that it's an many to many relationship ==> the project have many employ work to make it done, and one employe could have many project to work on
- the source code for the model=>
```
@Entity
@Table(name = "Employee")
public class Employee { 
    // ...
 
    @ManyToMany(cascade = { CascadeType.ALL })
    @JoinTable(
        name = "Employee_Project", 
        joinColumns = { @JoinColumn(name = "employee_id") }, 
        inverseJoinColumns = { @JoinColumn(name = "project_id") }
    )
    Set<Project> projects = new HashSet<>();
   
    // standard constructor/getters/setters
}
```
```
@Entity
@Table(name = "Project")
public class Project {    
    // ...  
 
    @ManyToMany(mappedBy = "projects")
    private Set<Employee> employees = new HashSet<>();
    
    // standard constructors/getters/setters   
}
```
- in this project you can see the we have to use==> 1) marven dependencie 2) marven configuration
- the relation between the two tables is bi-directional so every one of them have a reference to another one
- related to junit test for many to many relation ship could done with following code:
```
public class HibernateManyToManyAnnotationMainIntegrationTest {
    private static SessionFactory sessionFactory;
    private Session session;

    // ...

    @Test
    public void givenData_whenInsert_thenCreatesMtoMrelationship() {
        String[] employeeData = { "Peter Oven", "Allan Norman" };
        String[] projectData = { "IT Project", "Networking Project" };
        Set<Project> projects = new HashSet<>();

        for (String proj : projectData) {
            projects.add(new Project(proj));
        }

        for (String emp : employeeData) {
            Employee employee = new Employee(emp.split(" ")[0], 
              emp.split(" ")[1]);
 
            assertEquals(0, employee.getProjects().size());
            employee.setProjects(projects);
            session.persist(employee);
 
            assertNotNull(employee);
        }
    }

    @Test
    public void givenSession_whenRead_thenReturnsMtoMdata() {
        @SuppressWarnings("unchecked")
        List<Employee> employeeList = session.createQuery("FROM Employee")
          .list();
 
        assertNotNull(employeeList);
 
        for(Employee employee : employeeList) {
            assertNotNull(employee.getProjects());
        }
    }

    // ...
}
```