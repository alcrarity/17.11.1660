# 17.11.1660
tugas uas pemrograman

#include <iostream>
#include <conio.h>
#include <string>

using namespace std;

class tiket{
public:
	void setNama(string n){
		nama=n;
	}
	void setJumlah(int j){
		jumlah=j;
	}
	void setKelas(int k){
		kelas=k;
	}
	void setTujuan(string t){
		tujuan=t;
	}
protected:
	string nama;
	int jumlah;
	int kelas;
	string tujuan;
};

class kereta: public tiket{
public:
	int jgSmg(int jumlah, int kelas){
		return (250000 * kelas) * jumlah;
	}
	int jgSlo(int jumlah, int kelas){
		return (150000 * kelas) * jumlah;
	}
	int jgSby(int jumlah, int kelas){
		return (350000 * kelas) * jumlah;
	}
protected:

	int harga;
};

class bus: public tiket{
public:
	int jgBdg(int jumlah,int kelas){
		return(150000*kelas)*jumlah;
	}
	int jgJkt(int jumlah,int kelas){
		return(200000*kelas)*jumlah;
	}
	int jgMl(int jumlah,int kelas){
		return(100000*kelas)*jumlah;
	}
protected:
	int harga;
};

void menukereta(kereta krt){
	string nama;
	int kelas, tujuan, jumlah;
	cout<<"Nama : ";
	cin>>nama;
	cout<<"Tujuan [1. semarang |2.  solo |3. surabaya] : ";
	cin>>tujuan;
	cout<<"Kelas [1. ekonomi |2. bisnis] : ";
	cin>>kelas;
	cout<<"Jumlah : ";
	cin>>jumlah;

	switch(tujuan){
		case 1 : 
			cout<<" Total Pembayaran : "<<krt.jgSmg(jumlah, kelas);
			break;
		case 2 :
			cout<<" Total Pembayaran : "<<krt.jgSlo(jumlah, kelas);
			break;
		case 3 :
			cout<<" Total Pembayaran : "<<krt.jgSby(jumlah, kelas);
			break;
	}
}

void menubus(bus bs){
	string nama;
	int kelas, tujuan, jumlah;
	cout<<"Nama : ";
	cin>>nama;
	cout<<"Tujuan [1. Bandung |2.  Jakarta |3. Malang] : ";
	cin>>tujuan;
	cout<<"Kelas [1. ekonomi |2. bisnis] : ";
	cin>>kelas;
	cout<<"Jumlah : ";
	cin>>jumlah;

	switch(tujuan){
		case 1 : 
			cout<<" Total Pembayaran : "<<bs.jgBdg(jumlah, kelas);
			break;
		case 2 :
			cout<<" Total Pembayaran : "<<bs.jgJkt(jumlah, kelas);
			break;
		case 3 :
			cout<<" Total Pembayaran : "<<bs.jgMl(jumlah, kelas);
			break;
	}
}

int main(void){
	kereta krt;
	bus bs;
	int pilihan;

	cout<<"Selamat Datang Di Aplikasi Pembelian Tiket Kereta Api dan Bus"<<endl;
	cout<<"Pilih Moda Transportasi Anda : "<<endl;
	cout<<"1.Kereta Api"<<endl;
	cout<<"2.Bus"<<endl;
	cin>>pilihan;

	switch(pilihan){
		case 1 : 
			menukereta(krt);
			break;
		case 2 :
			menubus(bs);
			break;
	}
	return 0;
}
