# student
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class JDBCExample {
   static final String DB_URL = "jdbc:mysql://localhost/";
   static final String USER = "guest";
   static final String PASS = "guest123";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
         String sql = "CREATE DATABASE STUDENTS";
         stmt.executeUpdate(sql);
         System.out.println("Database created successfully...");   	  
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }

]}
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;
//CREATE
public class JDBCExample {
   static final String DB_URL = "jdbc:mysql://localhost/TUTORIALSPOINT";
   static final String USER = "guest";
   static final String PASS = "guest123";
  public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
          String sql = "CREATE TABLE STUDENT" +NO INT (3),NAME TEXT "VARCHAR(30)",DOB DATE"INT(10)",DOJ DATE "INT(8)";, " +          stmt.executeUpdate(sql);       System.out.println("Created table in given database...");   	  
      } catch (SQLException e) { e.printStackTrace();
      } }}
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
//UPDATE
public class JDBCExample {
   static final String DB_URL = "jdbc:mysql://localhost/TUTORIALSPOINT";
   static final String USER = "guest";
   static final String PASS = "guest123";
   static final String QUERY = "SELECT NO, NAME, DOB DATE, DOJ DATE FROM STUDENT";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
         String sql = "UPDATE STUDENT " +
            "SET NO = 30 WHERE NO in (100, 101)";
         stmt.executeUpdate(sql);
         ResultSet rs = stmt.executeQuery(QUERY);
         while(rs.next()){
            //Display values
            System.out.print("NO: " + rs.getInt("NO"));
            System.out.print(", NAME: " + rs.getInt("NAME"));
            System.out.print(", DOB DATE: " + rs.getString("DOB DATE"));
            System.out.println(", DOJ DATE: " + rs.getString("DOJ DATE"));
         }
         rs.close();
      } catch (SQLException e) {
         e.printStackTrace();
     }}}

//DELETE

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class JDBCExample {
   static final String DB_URL = "jdbc:mysql://localhost/TUTORIALSPOINT";
   static final String USER = "guest";
   static final String PASS = "guest123";
   static final String QUERY = "SELECT  NO,NAME, DOB DATE, DOJ DATE FROM STUDENT";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
         String sql = "DELETE FROM STUDENT " +
            "WHERE NO = 101";
         stmt.executeUpdate(sql);
         ResultSet rs = stmt.executeQuery(QUERY);
         while(rs.next()){
            //Display values
            System.out.print("NO: " + rs.getInt("NO"));
            System.out.print(", NAME: " + rs.getInt("NAME"));
            System.out.print(", DOB DATE: " + rs.getString("DOB DATE"));
            System.out.println(", DOJ DATE: " + rs.getString("DOJ DATE"));
         }
         rs.close();
      } catch (SQLException e) {  e.printStackTrace();
}}}
