#include<iostream>
#include<cstring>
#include<fstream>

using namespace std;
struct WORD{   //����һ���ṹ��
	int count;
	char s;

}w[100];

bool isword(char a[])//�ж��Ƿ���һ������
{
	int i = 0;
	for (i = 0; a[i] != '\0'; i++)
	if ((a[i] >= 'a' && a[i] <= 'z') || (a[i] >= '0' && a[i] <= '9'))
		return true;
	else
		return false;
}

int judgle(char b[], int n)   //�жϸõ����Ƿ���ֹ�
{
	if (n>0)
	for (int i = 0; i <n; i++)
	{
		if (!strcmp(b, &w[i].s))  //����
		{
			w[i].count++;
			return -1;
		}
	}
}
void SortWordDown(Word * words, int size)  //�Ե��ʳ���Ƶ�ʽ������е��ʣ�words �������飬size ��������
{
    for(int i=0;i<size;i++)  
    {
        for(int j=0;j <size-1;j++)  
        { 
            if(words[j].Count<words[j+1].Count)  
            {  
                words[j].exchange(words[j+1]);  
            }  
        }  
    }  
}  
int main(void)
{
	char result[500];

	char *ptr;
	ifstream file("c://A_Tale_of_Two_Cities.txt");   //��ȡ
	if (!file){ cout << "���ܴ��ļ�"; }
	while (!file.eof())
	{
		file.getline(result, 500);
	}
	file.close();
	int j = 0;//��дתСд
	while (result[j] != '/0'&&result[j + 1] != '/0')
	{
		if (result[j] >= 'A'&& result[j] <= 'Z')
		{
			result[j] = result[j] - 'A' + 'a';
			j++;
		}
	}
	cout << result;
	char *sep = " ";

	int i = 0;
	ptr = strtok(result, " ");  //����strtok�������ָ�result�ַ����еĵ���
	while (ptr != NULL){
		if (isword(p) != false)
		{
			if (judgle(p, n) != false)
			{
				w[n].s = *p; //��ֵ������
				n++;
			}
		}
		ptr = strtok(NULL, " ");

	}
}
int main()
{
	char c[200];
	ifstream fin("D:/A_Tale_of_Two_Cities.txt");   //���ĵ��л�ȡ�ַ���
	for (int f = 0;; f++)
		fin >> c[f];
	fin.close();
	cin.get();
	lwr(c);
	const char *delim = ",����.''!?";      //�ָ��ַ���
	char *q;
	int n = 0;
	q = strtok(c, delim);
	SortWordDown(words, wCount);
	while (q)
	{
		if (identify(q))
		{

			strcpy(test[n].p, q);
			n++;

		}


		q = strtok(NULL, delim);

		cout << "����ͳ�Ƴ���Ƶ����ָ�����ʣ�\n";
		char r;
		cin >> r;
		int t = 0;
		while (!strcmp(test[n].p, r))     //�ҵ�ָ������
		{
			t++;
		}
		cout << test[n].p << ":" << test[n].count << '\n';    //���ָ�����ʵ�ͳ�ƽ��
		return 0;
	}