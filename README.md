Download Link: https://assignmentchef.com/product/solved-cs310-data-structures-programming-assignment-5-hashing-with-sets-and-maps
<br>
<p style="font-weight: 400;"><strong><em>Problem Scenario</em></strong>

<p style="font-weight: 400;">The brokerage office was very impressed with your work from Assn 3. Nevertheless, the IT director at the office just received the latest “Java Geek Weekly”, and read all about hashing. Now, the IT director wants to replace the linked lists in your project with hash sets and maps.

<p style="font-weight: 400;">In addition, the brokerage office would like help their FundManagers identify specific stocks as either taxable or not taxable. Therefore, they would like to replace your prior reports with a report on this.

<p style="font-weight: 400;"><strong><em>Program Requirements</em></strong>

<p style="font-weight: 400;">You will replace your <strong>FundManagerImpl </strong>and <strong>StockTradeLogImpl </strong>classes from Assn 3 to work with hash tables, instead of linked lists.

<p style="font-weight: 400;">The <strong>FundManagerImpl </strong>will use a Hash Set to store <strong>FundManager </strong>objects. The hash table will be implemented as an array of FundManager objects (initialized to <strong>null </strong>when the table is created). The hash table will use the <strong><em>open addressing method </em></strong>via linear probing to resolve collisions. The array size for this implementation will be 19 (a prime number).

<p style="font-weight: 400;">The <strong>StockTradeLogImpl </strong>will use a hashmap to store StockTrade objects. You will need to create a <strong>MapEntry </strong>class to implement the hashmap. Each MapEntry will be comprised of a key and a <strong>StockTrade </strong>node. The hashmap will be an array of MapEntry objects (initialized to null when the table is created).

<p style="font-weight: 400;">Since the MapEntry value is a <strong>StockTradeNode</strong>, it can be used as a reference to a linked list. So, if there are multiple entries that map to the same index, the collisions will be resolved by using the <strong><em>chaining method</em></strong>, adding each entry to the top of the linked list at that index. This means that each <strong>StockTrade </strong>object that maps to the same index (via the hashcode) will be stored in a linked list at that index. The array size for this implementation will be 17 (another prime number).

<p style="font-weight: 400;"><em>See the last page of this requirements document for diagrams of the hash tables.</em>

<p style="font-weight: 400;">You will create your own hashing algorithms for this assignment. Remember the hashcode method that was generated for you in week 1? Modify this method for each of your domain classes.

<p style="font-weight: 400;">Create a hashcode for a <strong>FundManager </strong>object in the <strong>FundManagerImpl </strong>hash table by extracting the last 5 digit characters from the FundManager license number, converting them to an integer, and then using the modulus operator, so that the value will map correctly to array indexes. For example, the license number of CCC12233, will hash to:

<p style="font-weight: 400;">12233 mod 19 = 16 (maps to index 16)

<p style="font-weight: 400;">Create a hashcode for a <strong>StockTrade </strong>object in the <strong>StockTradeLogImpl </strong>hash table by adding the ASCII/Unicode values of each character in the stockSymbol. After adding them, use the modulus operator, so that the value will map correctly to an array index. For example, the StockSymbol of CCDD will hash to:

<p style="font-weight: 400;">67 + 67 + 68 + 68 = 270 mod 17 = 15 (maps to index 15)

<p style="font-weight: 400;">

<p style="font-weight: 400;">The input file of FundManagers and StockTrade listings will remain the same as used in the previous assignments, except that <strong>you can now assume all data will be valid</strong>. So there will no longer be any need to validate and remove incorrect data.

<p style="font-weight: 400;"><strong>You also will not need to worry about removing StockTrades or FundManagers</strong>. Concentrate on adding the objects to the respective HashSet/HashMap. You will need to remove the code in your main that removes the objects.

<p style="font-weight: 400;">Read the input file and use the correct hashCode to place each FundManager/StockTrade object into the correct location in one of the hash tables. Then display the contents of each hash table as follows:

<p style="font-weight: 400;">Add a <strong>displayHash() </strong>method to both <strong>FundManagerImpl </strong>and <strong>StockTradeLogImpl</strong>.

<p style="font-weight: 400;">These methods will first display a header:

<p style="font-weight: 400;">FundManager Hash Table: OR StockTrade Hash Table:

<p style="font-weight: 400;">and will then display where each FundManager/StockTrade object is stored in the hash table. An example is shown at the end of the assignment

<p style="font-weight: 400;">NOTE: The input in the example will provide collisions on both the FundManager and StockTrades HashSet/HashMap. You may use it to test your code. However, you are expected to provide your own data input files with a minimum of five FundManagers, each with at least two StockTrades. Your data needs to be as such to cause some collisions.

<p style="font-weight: 400;">Note that your <strong>FundManagerImpl </strong>and <strong>StockTradeLogImpl </strong>will no longer use <strong>remove </strong>methods (because no data will be removed from the hash tables). Instead, they will use <strong>add</strong>and <strong>find </strong>methods.

<p style="font-weight: 400;">The <strong>add </strong>methods will be used to place the <strong>FundManager </strong>and <strong>StockTrade </strong>objects into their hash tables.

<p style="font-weight: 400;">The <strong>find </strong>method in the <strong>FundManagerImpl </strong>class will search for a <strong>FundManager </strong>based on the FundManager license number. It will return a reference to the found FundManager object, or will return <strong><em>null </em></strong>if the FundManager is not in the hash table.

<p style="font-weight: 400;">The <strong>find </strong>method in the <strong>StockTradeLogImpl </strong>class will search for a <strong>StockTrade </strong>based on the stockSymbol. It will return a reference to the found StockTrade object, or will return <strong><em>null</em></strong>if the StockTrade is not in the hash table.

<p style="font-weight: 400;">You will not need to create any of the reports that you created in the past assignments. So you can remove the calls that created those reports from your <strong>main </strong>method.

<p style="font-weight: 400;">Instead, the brokerage office wants you use the hash tables to create a new report of taxable/not taxable stocks by FundManager for them. The office will provide a simple flat file of FundManager license numbers and StockTrade stockSymbols, for all of the FundManagers in the office who requested a report on their taxable/not taxable stocks.

<p style="font-weight: 400;">Each line of the file will contain a FundManager license number and a list of one or more StockTrade stockSymbols that the FundManager would like to check taxable/not taxable status on.

<p style="font-weight: 400;">For example (this is using the sample data at the end of the assignment):

<p style="font-weight: 400;"><strong>LMN11111 LMN XXXX</strong>

<p style="font-weight: 400;"><strong>MMM11111 MMM</strong>

<p style="font-weight: 400;"><strong>ABC11111 ABC</strong>

<p style="font-weight: 400;">This file, called <strong>FundManagerRequests.txt</strong>, will be located in the <strong>input </strong>folder

<p style="font-weight: 400;">When reading the data in this file:

<p style="font-weight: 400;">Use a hash code to find the FundManager license number in your <strong>FundManagerImpl </strong>hash table

<p style="font-weight: 400;">Use a hash code find each StockTrade stockSymbol your <strong>StockTradeLogImpl </strong>hash table

<p style="font-weight: 400;">and for each, determine if the StockTrade is taxable/not taxable.

<p style="font-weight: 400;">Replace the old create report method in <strong>PrintImpl </strong>with a method that will generate a new report to be written to an output file named <strong>assn5salesReport.txt</strong>, which will be located in the <strong>output </strong>folder of the project.

<p style="font-weight: 400;">Sample report output:

<p style="font-weight: 400;"><strong>FundManager LMN11111, George Harrison</strong>

<p style="font-weight: 400;"><strong>StockTrade LMN is NOT TAXABLE</strong>

<p style="font-weight: 400;"><strong>StockTrade XXXX is NOT TAXABLE</strong>

<p style="font-weight: 400;"><strong>FundManager MMM11111, Ringo Starr</strong>

<p style="font-weight: 400;"><strong>StockTrade MMM is TAXABLE</strong>

<p style="font-weight: 400;"><strong>FundManager ABC11111 does not exist</strong>

<p style="font-weight: 400;">Note that when the <strong>FundManager </strong>does not exist, you should not search for any of the <strong>StockTrade </strong>listings on that line.

<p style="font-weight: 400;">The program must follow all <strong>CS310 Coding Standards </strong>from Content section 1.9.

<p style="font-weight: 400;"><strong>Additional Requirements</strong>

<p style="font-weight: 400;"> Create <strong>Javadoc headers</strong>, and generate <strong>Javadoc files </strong>for each of your new <strong><em>implementation </em></strong>classes and for all new static methods in the main class. You are responsible for completing the comment headers created.

<p style="font-weight: 400;"> Your original input data file (containing <strong>FundManager </strong>and <strong>StockTrade </strong>data to build the hash tables from) will still be read from the <strong>input </strong>folder in your project.

<p style="font-weight: 400;">

<p style="font-weight: 400;">Place all test data files that you create to test your program in the <strong>input </strong>folder of your project, and name them as follows:

<p style="font-weight: 400;"><strong>assn5input1.txt</strong>

<p style="font-weight: 400;"><strong>assn5input2.txt</strong>

<p style="font-weight: 400;">(i.e. number each data file after the filename of <strong>assn5input.txt</strong>)

<p style="font-weight: 400;"> Your new input data file will also be read from the <strong>input </strong>folder in your project.

<p style="font-weight: 400;">

<p style="font-weight: 400;">Place all test data files that you create to test your program in the <strong>input </strong>folder of your project, and name them as follows:

<p style="font-weight: 400;"><strong>FundManagerRequests1.txt</strong>

<p style="font-weight: 400;"><strong>FundManagerRequests2.txt</strong>

<p style="font-weight: 400;">(i.e. number each data file after the filename of <strong>FundManagerRequests.txt</strong>)

<p style="font-weight: 400;">As a group, all of your test data files should demonstrate that you have tested every possible execution path within your code, including erroneous data which causes errors or exceptions.

<p style="font-weight: 400;"> Add screen shots of <strong>clean compile </strong>of your classes to the documentation folder.

<p style="font-weight: 400;">

<p style="font-weight: 400;">WARNING: Submittals without the clean compile screenshots will <strong>not </strong>be accepted.

<p style="font-weight: 400;">(This means that programs that do not compile will <strong>not </strong>be accepted)

<p style="font-weight: 400;">

<p style="font-weight: 400;">StockTrade

<p style="font-weight: 400;">NEXT

<p style="font-weight: 400;">KEY

<p style="font-weight: 400;">StockTrade

<p style="font-weight: 400;">NEXT

<p style="font-weight: 400;"><strong>Program Submission</strong>

<p style="font-weight: 400;">Programming assignment is due by <span data-term="goog_1630767388">midnight</span> of the date listed on <strong>Course Assignments by Week </strong>page.

<p style="font-weight: 400;"> Export your project from NetBeans using the same method as you did for previous assns.

<p style="font-weight: 400;">o Name your export file in the following format: <strong>CS310&lt;lastname&gt;Assn&lt;x&gt;.zip</strong>

<p style="font-weight: 400;">

<p style="font-weight: 400;">For example:

<p style="font-weight: 400;"><strong>CS310SmithAssn5.zip</strong>

<p style="font-weight: 400;"> Submit your <strong>.zip </strong>file to the <strong>Prog Assn 5 </strong>Submission Folder (located under <strong>Assignments </strong>tab in online course). Only NetBeans export files will be accepted.

<p style="font-weight: 400;">

<p style="font-weight: 400;"><strong>Grading</strong>

<p style="font-weight: 400;">This program will be graded using the <strong>rubric </strong>that is linked under the online <strong>Student Resources </strong>page.

<p style="font-weight: 400;"><strong><em>WARNING: </em></strong><em>Programs submitted more than 5 days past the due date will <strong>not </strong>be accepted, and will receive a grade of 0.</em>

<p style="font-weight: 400;"><strong>HashSet Diagram for FundManagers</strong>

<p style="font-weight: 400;">Each index of the array represents the hashcode.

<p style="font-weight: 400;"><strong>HashMap Diagrams for StockTrades</strong>

<p style="font-weight: 400;">StockTradeNode

<p style="font-weight: 400;">MapEntry

<p style="font-weight: 400;">(the <strong>key </strong>is used to determine the hashcode,

<p style="font-weight: 400;">and the value is a StockTradeNode object)

<p style="font-weight: 400;">

<p style="font-weight: 400;">The hash map is an array of MapEntry objects:

<p style="font-weight: 400;">EXAMPLE AUDIT TRAIL

<p style="font-weight: 400;">For the following data input:

<p style="font-weight: 400;"><strong>BROKER,ADD,MMM11111,Ringo,Starr,321-111,0.02</strong>

<p style="font-weight: 400;"><strong>TRADE,BUY,MMM,999.999,99999,MMM11111,Y</strong>

<p style="font-weight: 400;"><strong>BROKER,ADD,LMN11111,George,Harrison,123-222,0.025</strong>

<p style="font-weight: 400;"><strong>TRADE,BUY,LMN,9,1022,LMN11111,N</strong>

<p style="font-weight: 400;"><strong>TRADE,BUY,ABC,555,555,LMN11111,Y</strong>

<p style="font-weight: 400;"><strong>TRADE,BUY,XXXX,100,877,LMN11111,N</strong>

<p style="font-weight: 400;">and sample request file on page 2, the following audit trail is generated:

<p style="font-weight: 400;"><strong>Reading data from file input/assn5input.txt</strong>

<p style="font-weight: 400;"><strong>ADDED: FundManager with license MMM11111</strong>

<p style="font-weight: 400;"><strong>ADDED: StockTrade with stock symbol MMM listed by fundManager MMM11111</strong>

<p style="font-weight: 400;"><strong>ADDED: FundManager with license LMN11111</strong>

<p style="font-weight: 400;"><strong>ADDED: StockTrade with stock symbol LMN listed by fundManager LMN11111</strong>

<p style="font-weight: 400;"><strong>ADDED: StockTrade with stock symbol ABC listed by fundManager LMN11111</strong>

<p style="font-weight: 400;"><strong>ADDED: StockTrade with stock symbol XXXX listed by fundManager LMN11111</strong>

<p style="font-weight: 400;"><strong>Done reading file. 6 lines read</strong>

<p style="font-weight: 400;"><strong>FundManager Hash Table:</strong>

<p style="font-weight: 400;"><strong>Index 0 is empty</strong>

<p style="font-weight: 400;"><strong>Index 1 is empty</strong>

<p style="font-weight: 400;"><strong>Index 2 is empty</strong>

<p style="font-weight: 400;"><strong>Index 3 is empty</strong>

<p style="font-weight: 400;"><strong>Index 4 is empty</strong>

<p style="font-weight: 400;"><strong>Index 5 is empty</strong>

<p style="font-weight: 400;"><strong>Index 6 is empty</strong>

<p style="font-weight: 400;">

<p style="font-weight: 400;"><strong>Index 7 is empty</strong>

<p style="font-weight: 400;"><strong>Index 8 is empty</strong>

<p style="font-weight: 400;"><strong>Index 9 is empty</strong>

<p style="font-weight: 400;"><strong>Index 10 is empty</strong>

<p style="font-weight: 400;"><strong>Index 11 is empty</strong>

<p style="font-weight: 400;"><strong>Index 12 is empty</strong>

<p style="font-weight: 400;"><strong>Index 13 is empty</strong>

<p style="font-weight: 400;"><strong>Index 14 is empty</strong>

<p style="font-weight: 400;"><strong>Index 15 contains FundManager MMM11111, Ringo Starr</strong>

<p style="font-weight: 400;"><strong>Index 16 contains FundManager LMN11111, George Harrison</strong>

<p style="font-weight: 400;"><strong>Index 17 is empty</strong>

<p style="font-weight: 400;"><strong>Index 18 is empty</strong>

<p style="font-weight: 400;"><strong>StockTrade Hash Table:</strong>

<p style="font-weight: 400;"><strong>Index 0 is empty</strong>

<p style="font-weight: 400;"><strong>Index 1 is empty</strong>

<p style="font-weight: 400;"><strong>Index 2 is empty</strong>

<p style="font-weight: 400;"><strong>Index 3 is empty</strong>

<p style="font-weight: 400;"><strong>Index 4 is empty</strong>

<p style="font-weight: 400;"><strong>Index 5 is empty</strong>

<p style="font-weight: 400;"><strong>Index 6 is empty</strong>

<p style="font-weight: 400;"><strong>Index 7 is empty</strong>

<p style="font-weight: 400;"><strong>Index 8 is empty</strong>

<p style="font-weight: 400;"><strong>Index 9 is empty</strong>

<p style="font-weight: 400;"><strong>Index 10 contains StockTrades: LMN MMM</strong>

<p style="font-weight: 400;"><strong>Index 11 contains StockTrades: ABC</strong>

<p style="font-weight: 400;"><strong>Index 12 contains StockTrades: XXXX</strong>

<p style="font-weight: 400;"><strong>Index 13 is empty</strong>

<p style="font-weight: 400;"><strong>Index 14 is empty</strong>

<p style="font-weight: 400;"><strong>Index 15 is empty</strong>

<p style="font-weight: 400;"><strong>Index 16 is empty</strong>

<p style="font-weight: 400;"><strong>Creating initial report…</strong>

<p style="font-weight: 400;"><strong>Creating sales report using requests from file input/FundManagerRequests.txt</strong>

<p style="font-weight: 400;"><strong>Sales report is complete — located in file: output/assn5taxReport.txt</strong>ort.txt