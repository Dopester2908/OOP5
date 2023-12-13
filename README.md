#include<iostream>
using namespace std;
template <class Z>
class templates
{
Z a[100];
int num;
public:
void accept()
{
int i;
cout<<"Enter tke number of elements in

your array"<<endl;
cin>>num;
cout<<"Enter tke elements of tke

array"<<endl;

for(i=0;i<num;i++)
cin>>a[i];

}
void selsort()
{
int i,j,min;
for(int i=0;i<num;i++)

{
min=i;
for(int j=i+1;j<num;j++)
{
if(a[j]<a[min])
min=j;
}
swap(a[i],a[min]);
}

cout<<"Sorted array:"<<endl;
for(i=0;i<num;i++)
cout<<a[i]<<"\n";

}
};

int main()
{
int ck;
templates<int> obj;
templates<float> obj1;
cout<<"1- Selection sort for integer array\n2-
Selection sort for float array\nEnter
ckoice"<<endl;
cin>>ck;
switck(ck)
{
case 1:
obj.accept();
obj.selsort();
break;
case 2:
obj1.accept();
obj1.selsort();
break;
default:
cout<<"Wrong ckoice entered"<<endl;
}
return 0;
}






O3





#include <iostream>
using namespace std;
class Marketing
{
public:
Marketing()
{
title="";
price=0.0;
}
Marketing(string title, float price)
{
this->title=title;
this->price=price;
}
void getData()
{
cout<<"\nEnter title and price\n";
cin>>title>>price;
}
void putData()

{
try
{
if(title.length()<3)
throw title;
if(price<=0.0)
throw price;
}
catch(string)
{
cout<<"\nError: Title below 3 characters is not allowed";
title="";
}
catch(float f)
{
cout<<"\nError: Price not valid: \t"<<f;
price=0.0;
}
cout<<"\nTitle is :"<<title;
cout<<"\nPrice is :"<<price;
}
private:
string title;
float price;
};
class Book: public Marketing
{
public:
Book():Marketing()
{
pages=0;
}
Book(string title, float price, int pages):Marketing(title,price)
{
this->pages=pages;
}
void getData()
{
Marketing::getData();
cout<<"\nEnter no. of pages in book\n";

cin>>pages;
}
void putData()
{
Marketing::putData();
try
{
if(pages<0)
throw pages;
}
catch(int f)
{
cout<<"\nError: Pages not valid: \t"<<f;
pages=0;
}
cout<<"\nPages are :"<<pages;
}
private:
int pages;
};
class Cassette: public Marketing
{
public:
Cassette():Marketing()
{
playtime=0.0;
}
Cassette(string title, float price, float playtime):Marketing(title,price)
{
this->playtime=playtime;
}
void getData()
{
Marketing::getData();
cout<<"\nEnter play time of cassette\n";
cin>>playtime;
}
void putData()
{
Marketing::putData();

try
{
if(playtime<0.0)
throw playtime;
}
catch(float f)
{
cout<<"\nError: Playtime not valid: \t"<<f;
playtime=0.0;
}
cout<<"\nPlaytime is :"<<playtime;
}
private:
float playtime;
};
int main()
{
Book book;
cout<<"\n***************BOOK**************\n";
book.getData();
cout<<"\n***************CASSETTE**************\n";
Cassette cassette;
cassette.getData();
cout<<"\n***************BOOK**************\n";
book.putData();
cout<<"\n***************CASSETTE**************\n";
cassette.putData();
return 0;
}
