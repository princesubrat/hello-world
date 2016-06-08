import java.sql.*;
public class CreateTable {

	public static void main(String[] args) throws SQLException,ClassNotFoundException {
		// TODO Auto-generated method stub
		
Connection con = prepareConnection();
Statement st = con.createStatement();
String query = "Create table emtab(ID int,NAME varchar2(20),SALARY float)";
st.executeUpdate(query);
System.out.println("Table created successfully");
con.close();
	}
public static Connection prepareConnection() throws SQLException,ClassNotFoundException{
	DriverManager.registerDriver(new oracle.jdbc.driver.OracleDriver());
	Connection con = DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521","hr","qwerty");
return con;	
}
}
