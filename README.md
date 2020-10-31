# ProjectOctober
This is where you will be storing your source codes. 
Hello! This is my Random Password Generator code. It's no where near good or perfect, but its something, and random.

#include <stdio.h>
#include <conio.h>
#include <iostream>
#include <string.h>
using namespace std;


int main()
{
    int day{}, month{}, year{};
    char choice {};
	cout<<"Welcome to Random Password Generation Site"<<endl;
    cout<<"Press 'Y' if you wish to continue to Password Generation and 'N' to abort"<<endl;
    cin>>choice;
    if (choice=='y'||choice=='Y')
    {
        string name{};
        cout<<"Enter your name"<<endl;
        cin>>name;
        cout<<"Enter DOB in YYYYMMDD format"<<endl;
        cout<<"Year: ";
        cin>>year;
        if(year<=1930||year>=2020)
        {
            cout<<"You are not eligible for this site. Sorry!"<<endl;
            exit(0);
        }
        else
         {
           cout<<endl<<"Month: ";
           cin>>month;
           if (month<=0||month>12)
            {
            cout<<"Please enter a proper month."<<endl;
            exit(0);
            }
           else
           {
            cout<<endl<<"Day: ";
            cin>>day;
           }
           if (day>31)
           {
               cout<<"Enter a proper date."<<endl;
               exit(0);
           }
           else if (month==2&&day>28)
           {
               cout<<"Enter a proper date."<<endl;
               exit(0);
           }
           else if ((month==4||month==6||month==9||month==11)&&(day>30))
           {
               cout<<"Enter a proper date."<<endl;
               exit(0);
           }
         }
           
           
           
           
           
        cout<<endl;
        string *val1;
        int *val2;
        val1=&name;
        val2=&year;
        int x = reinterpret_cast<uintptr_t>(val1);
        int y = reinterpret_cast<uintptr_t>(val2);
        //cout<<x<<endl<<y<<endl;  OKAY
        
        cout<<"How many random passwords do you want to generate?"<<endl;
        int num{};
        cin>>num;
        for (int i{0};i<num;i++)
        {
         long int z=(rand()%1000);
         long int w=((((x/z)+y)/year)*(i+day)*(i+1))*month*day; //OKAY
         string s=to_string(w);
         //cout<<s<<endl; OKAY
         for (int k=0;k<=s.length();k++)
         {
            if (s[k]=='0')
            {
                s[k]='!';
            } 
            else if (s[k]=='1')
            {
                s[k]='a';
            }
            else if (s[k]=='2')
            {
                s[k]='p';
            }
            else if (s[k]=='3')
            {
                s[k]='s';
            }
            else if (s[k]=='4')
            {
                s[k]='@';
            }
            else if (s[k]=='5')
            {
                s[k]='t';
            }
            else if (s[k]=='6')
            {
                s[k]='q';
            }
            else if (s[k]=='7')
            {
                s[k]='f';
            }
            else if (s[k]=='8')
            {
                s[k]='*';
            }
            else if (s[k]=='9')
            {
                s[k]='_';
            }
         }
         cout<<"Password "<<(i+1)<<" is:"<<s<<endl;
         //cout<<"Password "<<i<<"is : "<< 
        }
        
    }
    else if (choice=='n'||choice=='N')
    {
        cout<<"Exiting Random Password Generator. Thank You!"<<endl;
    }
    else
    {
       cout<<"Wrong Input. Try Again."<<endl;
       exit(0); 
    }

    
	return 0;
}
