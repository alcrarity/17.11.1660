# 17.11.1660
tugas uas pemrograman

#include <iostream>
#include <conio.h>
#include <string>
using namespace std;

class Pesan
{
protected:
	string penerima;
	string isi;
public:
	Pesan(string penerima, string isi){
		this->penerima = penerima;
		this->isi = isi;
	};

	virtual string kirim(){
		return 0;
	};
};


class Email : public Pesan
{
private:
	string email;
public:
	Email(string penerima, string isi, string email):Pesan(penerima, isi){
		this->penerima = penerima;
		this->isi = isi;
		this->email = email;
	};
	string kirim(string penerima, string isi, string email){
		cout<<"Mengirim pesan lewat email"<<endl<<endl;
		cout<<"Penerima : "<<penerima<<endl;
		cout<<"Email : "<<email<<endl;
		cout<<"Pesan : "<<isi<<endl;
		return 0;
	};
};

int main()
{
	string email = "adytyo.27@students.amikom.ac.id";
	Pesan *em = new Email(penerima, isi, email);
	cout<<"\n"<<em->kirim();

	getch();

	delete em;
	return 0;
}
