# HotlineCallCenter.cpp

1.	Data Model:
1.1.	
•	Const int Size=3;// it's constant values because Each user can own maximum of 3 lines, and its size is 4-byte.
•	Const int CardSize = 14; //it's constant values because every Serial Card has only 14 Numbers, and it's size is 4-byte.
•	Float Balance; //global variable, to hold its value throughout the lifetime of your program, and can be accessed by any function, and its size is 4-byte. 
•	Struct date : use it to collect data about day and month and year and grouped under one name(date), and its size is 12-byte  because it contains 3 data type of  int (an aggregate data type).
•	Struct lineInfo : use it to collect data about every line the user used like mobile number, package type, balance, start date, and renewal date, and grouped under one name(lineInfo), (an aggregate data type).
•	Struct user : use it to collect data about every user like  ID, e-mail, name, password, address, and set of lines, and grouped under one name(user), (an aggregate data type).
•	Int linesNum; //it's local variable, because it is declared inside one function(void user_data(int i)) , and its size is 4-byte.
•	String linesNumStr; //it's local variable, because it is declared inside one function(void user_data(int i)).
•	String mobileNumber; //local variable, because it is declared inside one function (void Renewreq(char request, int userIndex)).
•	 String type; //local variable, because it is declared inside one function (void Renewreq(char request, int userIndex)).
•	String mobile; //local variable, because it is declared inside one function (void Balancecheck(int userIndex)).
•	Char CardSerialNumber[CardSize]; //local variable, because it is declared inside one function(void Rechbalance(int userIndex)), and its size is 1-byte.
•	Bool error; //local variable, because it is declared inside one function(void Rechbalance(int userIndex)), and its size is 1-byte.
•	Int AmountOfMoney; //local variable, because it is declared inside one function(void Rechbalance(int userIndex)), and its size is 4-byte.
•	String phone; //local variable, because it is declared inside one function (void Rechbalance(int userIndex)).
•	Char hash; //local variable, because it is declared inside one function (void Rechbalance(int userIndex)), and its size is 1-byte.
•	String phone; //local variable, because it is declared inside one function (void Rechbalance(int userIndex)).
•	String name, mobile, mobileTransfer; //local variable, because it is declared inside one function (void Tranbalance(int userIndex, int users)).
•	Float balance;//local variable, because it is declared inside one function(void Tranbalance(int userIndex, int users)), and it's size is 4-byte.
•	Int lineIndex;//local variable, because it is declared inside one function(void Tranbalance(int userIndex, int users)), and it's size is 4-byte.
•	Char hash;//local variable, because it is declared inside one function(void Tranbalance(int userIndex, int users)), and it's size is 1-byte.
•	String id;//local variable, because it is declared inside one function (int login(int users)).
•	String password;//local variable, because it is declared inside one function (int login(int users)).
•	Int choise;//local variable, because it is declared inside one function(int main()),and it's size is 4-byte.
•	Int users;//local variable, because it is declared inside one function(int main()),and it's size is 4-byte.
•	Bool error;//local variable, because it is declared inside one function(int main()),and it's size is 1-byte.
•	Char request;//local variable, because it is declared inside one function(int main()), and its size is 1-byte.
•	Float AmountOfMoney;//local variable, because it is declared inside one function(int main()), and its size is 4-byte.
•	Int userIndex = login(users);//local variable, because it is declared inside one function(int main()), and its size is 4-byte.

1.2.	 How to validate the user inputs:

•	If a user submits data that is not within the allowed values or it is in the wrong format, it may cause the application to exhibit unexpected behavior – which may include a blank screen or a screen that doesn’t make sense. Validation allows for this to be prevented, and instead to present a human-readable error message back to the user, like input more that 3 lines, or input more that 14 number in card serial number, or Choose something other than the 5-options shown to him in menu function.
•	User could apply his first and last name in data function (name).
•	User should apply the same id and password in login function that he wrote first in data function.
•	User could apply the first name only of that someone he transfer amount of balance to him in tranbalance function.

2.Process Model (Functions):

•	Void CheckLines(lineInfo& l) //function For lines use to keep the mobile number, package type, balance, start date, and renewal date.
Inputs:
1.	string MobileNumber;
2.	string PackageType;
3.	Float Balance; 
4.	date StartDate;
5.	date RenewalDate;
               Outputs: 
Has no output, has no return value (its void function)

•	Void user_data(int i)//function for user's data use to keep ID, e-mail, name, password, address, and set of lines.
Inputs:
1.	string ID;
2.	string email;
3.	string name;
4.	string password;
5.	string address;
6.	lineInfo lines[Size];
Outputs: 
Has no output, has no return value (its void function)

•	Void Renewreq(char request, int userIndex) //function use to renew user's subscription.
Inputs:
1.	string mobileNumber;
2.	string type;
3.	int month; it's size is 4-byte.
4.	int day; it's size is 4-byte.
5.	int year; it's size is 4-byte.
Outputs: 
Has no output, has no return value (it's void function)

•	Void Balancecheck(int userIndex) //function use to check the balance and Discount the balance if user make a call or send a message.
Inputs: 
1.	string mobile;
Outputs: 
Has no output, has no return value (its void function)

•	Void Rechbalance(int userIndex) //function use to recharge user's balance by entering a card serial number with a specific amount of money.
Inputs:
1.	char CardSerialNumber[CardSize]; 
2.	bool error; 
3.	int AmountOfMoney; 
4.	string phone
5.	char hash;
Outputs: 
Has no output, has no return value (it's void function)

•	Void Tranbalance (int userIndex, int users) //function use to transfer amount of balance user1 to balance user2.
Inputs:
1.	string name;
2.	string mobile;
3.	string mobileTransfer;
4.	int balance;
5.	int lineIndex;
Outputs: 
Has no output, has no return value (its void function)

•	Int login (int users) //function use to allow the user to enter the system by login with his information.
Inputs:
1.	string id;
2.	string password;
Outputs:
Has return value (return i;) and it's data type is int.

•	Void main()
Inputs:
1.	Char choice;
2.	Int users;
3.	Bool error;
4.	Char request;
5.	Int userIndex = login(users);
 Outputs:
Has no output, has no return value (its void function)

3.Testing:

If you choose more than 1 user you should apply all the correct information for the number of users you choose.
  
![image](https://user-images.githubusercontent.com/101226388/189550965-388056f8-67ba-4b50-a86b-094f59d8227b.png)

If you choose more than 1 line (<=3), you should apply all the correct information of these lines.

![2](https://user-images.githubusercontent.com/101226388/189551081-7597e850-5d16-4c8b-9e0c-62bb481dea5b.png)


![3](https://user-images.githubusercontent.com/101226388/189551107-1fd9d387-d8eb-4de4-b396-c3bba1011d33.png)

![4](https://user-images.githubusercontent.com/101226388/189551113-79dce21d-2ec2-4cd0-a83c-23c2628a2d50.png)

If you choose 1:

If you choose c or C:

![5](https://user-images.githubusercontent.com/101226388/189551148-82d5ec5d-5233-4c6c-9c2d-4b1f124f2918.png)

![6](https://user-images.githubusercontent.com/101226388/189551154-04bd10b8-3554-4e60-941a-b53a25205d1e.png)

If you choose 1:

If you choose r or R:

![7](https://user-images.githubusercontent.com/101226388/189551175-0d29e31e-19d0-4fe2-992f-02a6001c4a14.png)

![8](https://user-images.githubusercontent.com/101226388/189551181-3f751c9b-aa6c-46fa-b91b-6361178c3d68.png)

If you choose 2:

![9](https://user-images.githubusercontent.com/101226388/189551197-6108f331-b790-44bb-844e-40b888f94986.png)

If you choose 3:

![10](https://user-images.githubusercontent.com/101226388/189551218-001f6b45-9eaa-421a-bce8-20f0483cb5d7.png)

![11](https://user-images.githubusercontent.com/101226388/189551236-ae2f8ffb-f7c2-494f-98f8-d7c51dab1a4f.png)

If you choose 4:

![12](https://user-images.githubusercontent.com/101226388/189551261-c8c934fa-3abb-461a-bae5-7fd0b1130792.png)

![13](https://user-images.githubusercontent.com/101226388/189551271-22a70517-89b9-4a16-b2db-eaa6236a1a13.png)

If you choose 5:

![14](https://user-images.githubusercontent.com/101226388/189551300-5ee7472d-1d22-4a49-9085-602a8c38b862.png)









