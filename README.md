Shopizer 2.0.5 (for java 1.8)
-------------------

Java open source e-commerce software

- Shopping cart
- Catalogue
- Search
- Checkout
- Administration


To get the code:
-------------------
Clone the repository:
$ git clone https://github.com/pratik143/shopizer-2.0.5.git

If this is your first time using Github, review http://help.github.com to learn the basics.

You can also download the zip file containing the code from https://github.com/pratik143/shopizer-2.0.5.git

To use mysql database:
-------------------
	do below configuration changes.
	For windows, open my.ini file (usually located in MySQL/MySQL x.x/my.ini)
 	set, lower_case_table_names=1 (By default it 1)
	For linux,
 	There is no internal MySQL command to trace this, it's a little too abstract. The file might be in 5 (or more?) locations, and they would all be valid because they load cascading
 	/etc/my.cnf
 	/etc/mysql/my.cnf
 	$MYSQL_HOME/my.cnf
 	[datadir]/my.cnf
 	~/.my.cnf
	
	Create SALESMANAGER database.
	do below changes in database.properies file, which located in "shopizer-2.3.0\sm-shop\src\main\resources\database.properies".
	uncomment mysql properies and comment in H2 properies as below,

	#------------------------------------------- do same config in database.properies ---------------------------------------
	#MYSQL
	db.jdbcUrl=jdbc:mysql://localhost:3306/SALESMANAGER?autoReconnect=true&useUnicode=true&characterEncoding=UTF-8
	db.user=root
	db.password=password
	db.driverClass=com.mysql.jdbc.Driver
	hibernate.dialect=org.hibernate.dialect.MySQL5InnoDBDialect
	#H2
	#db.jdbcUrl=jdbc\:h2\:file\:./SALESMANAGER;AUTOCOMMIT=OFF;;mv_store=false;INIT\=CREATE SCHEMA IF NOT EXISTS SALESMANAGER
	#db.user=test
	#db.password=password
	#db.driverClass=org.h2.Driver
	#hibernate.dialect=org.hibernate.dialect.H2Dialect	


To build the application:
-------------------	
From the command line with Maven installed:

	$ cd shopizer
	$ mvn clean install
	

Run the application from Tomcat 
-------------------
copy sm-shop/target/sm-shop.war to tomcat or any other application server deployment dir

Increase heap space to 1024 m or at least 512 m

### Heap space configuration in Tomcat:


If you are using Tomcat, edit catalina.bat for windows users or catalina.sh for linux / Mac users

	in Windows
	set JAVA_OPTS="-Xms1024m -Xmx1024m -XX:MaxPermSize=256m" 
	
	in Linux / Mac
	export JAVA_OPTS="-Xms1024m -Xmx1024m -XX:MaxPermSize=256m" 

Run the application from Spring boot 
-------------------

       $ cd sm-shop
       $ mvn spring-boot:run

Run the application from Spring boot in eclipse
-------------------

Right click on com.salesmanager.shop.application.ShopApplication

run as Java Application

### Access the application:
-------------------

Access the deployed web application at: http://localhost:8080/

Acces the admin section at: http://localhost:8080/admin

#####username : admin
#####password : password

The instructions above will let you run the application with default settings and configurations.
Please read the instructions on how to connect to MySQL, configure an email server and configure other subsystems


### Documentation:
-------------------

Documentation available from the wiki <https://github.com/shopizer-ecommerce/shopizer/wiki>

More documentation is available on shopizer web site here <http://www.shopizer.com>
