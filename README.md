<div align="center">

## link list


</div>

### Description

example for link list, it take name, adress, number of tickets, according to your choice sho w list....
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[RuhiTAS](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/ruhitas.md)
**Level**          |Beginner
**User Rating**    |2.8 (14 globes from 5 users)
**Compatibility**  |C, C\+\+ \(general\), Microsoft Visual C\+\+, Borland C\+\+, UNIX C\+\+
**Category**       |[Data Structures](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/data-structures__3-8.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/ruhitas-link-list__3-3231/archive/master.zip)





### Source Code

```
//Bu Program Ýsim,Adres ve Bilet sayýsýný
//alarak Link list yapýsýyla kaydeder ve Listeler
#include <stdlib.h>
#include <iostream.h>
struct LinkList
{
	char name[20];
	char adress[50];
	int NumTickets;
	LinkList *ptrnext;
};
void yeniKayit();
void listele();
LinkList *ptrfirst, *ptrthis, *ptrnew, *ptrlast;
void main()
{
	int ch;
	ptrfirst = ptrthis = ptrnew = ptrlast = NULL;
	cout<<"Seciminizi Yapiniz !!!\n!!!Isim ve Adreste BOSLUK(SPACE) Kullanmayiniz!!!\n";
	cout<< "\nYeni Kayit icin (1)";
	cout<< "\nListelemek icin (2)";
	cout<< "\nCikmak icin (55) giriniz";
	cout<<"\n SECIMINIZ ? = ";
	cin>>ch;
	while(ch!= 55)
	{
		switch(ch)
		{
			case 1:
				 yeniKayit();
				 break;
			case 2:
				 listele();
				 break;
			case 55:
				cout<<"Programdan Ciktiniz!!";
				exit(0);
			default : cout<<"\n !! Yanlis Secim !!";
		}
		cout<< "\nYeni Kayit icin (1)";
		cout<< "\nListelemek icin (2)";
		cout<< "\nCikmak icin (55) giriniz";
		cout<<"\n SECIMINIZ ? = ";
		cin>>ch;
	}
}
void yeniKayit()
{
	ptrnew = new LinkList;
	if(ptrfirst==NULL)
		ptrfirst = ptrlast = ptrnew;
	else
	{
		ptrlast->ptrnext = ptrnew;
		ptrlast = ptrnew;
	}
	cout<<"\nAdinizi Giriniz: ";cin >>ptrlast->name;
	cout<<"\nAdresiniz: ";cin >>ptrlast->adress;
	cout<<"\nBilet Sayisi Giriniz: ";cin >>ptrlast->NumTickets;
	ptrlast->ptrnext=NULL;
}
void listele()
{
	if(ptrfirst == NULL)
		cout<<"\nListe Bos!!\n";
	else
	{
		ptrthis=ptrfirst;
		do
		{
			cout<<"\nAd: "<<ptrthis->name
		    <<"\nAdres : "<<ptrthis->adress
		    <<"\nBilet Sayisi: "<<ptrthis->NumTickets;
			ptrthis = ptrthis->ptrnext;
		}
		while (ptrthis != NULL);
	}
}
```

