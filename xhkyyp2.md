#include<iostream>
#include<cstring>
#include<fstream>

using namespace std;
struct WORD{   //创建一个结构体
	int count;
	char s;

}w[100];

bool isword(char a[])//判断是否是一个单词
{
	int i = 0;
	for (i = 0; a[i] != '\0'; i++)
	if ((a[i] >= 'a' && a[i] <= 'z') || (a[i] >= '0' && a[i] <= '9'))
		return true;
	else
		return false;
}

int judgle(char b[], int n)   //判断该单词是否出现过
{
	if (n>0)
	for (int i = 0; i <n; i++)
	{
		if (!strcmp(b, &w[i].s))  //出现
		{
			w[i].count++;
			return -1;
		}
	}
}
void SortWordDown(Word * words, int size)  //以单词出现频率降序排列单词，words 单词数组，size 单词数量
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
	ifstream file("c://A_Tale_of_Two_Cities.txt");   //读取
	if (!file){ cout << "不能打开文件"; }
	while (!file.eof())
	{
		file.getline(result, 500);
	}
	file.close();
	int j = 0;//大写转小写
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
	ptr = strtok(result, " ");  //利用strtok函数来分割result字符串中的单词
	while (ptr != NULL){
		if (isword(p) != false)
		{
			if (judgle(p, n) != false)
			{
				w[n].s = *p; //赋值给数组
				n++;
			}
		}
		ptr = strtok(NULL, " ");

	}
}
int main()
{
	char c[200];
	ifstream fin("D:/A_Tale_of_Two_Cities.txt");   //从文档中获取字符串
	for (int f = 0;; f++)
		fin >> c[f];
	fin.close();
	cin.get();
	lwr(c);
	const char *delim = ",”“.''!?";      //分割字符串
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

		cout << "输入统计出现频数的指定单词：\n";
		char r;
		cin >> r;
		int t = 0;
		while (!strcmp(test[n].p, r))     //找到指定单词
		{
			t++;
		}
		cout << test[n].p << ":" << test[n].count << '\n';    //输出指定单词的统计结果
		return 0;
	}