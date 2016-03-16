#include <iostream>
#include <map>
#include <sstream>
#include <iomanip>
using namespace std;

void statistic(char str[])
{
	istringstream isstrm(str);
	string s;
	map<string, int> m;
	while (isstrm >> s) {
		for (string::size_type i = 0; i < s.size(); ++i)
			s[i] = tolower(s[i]);
		++m[s];
	}
	cout << setiosflags(ios::left) << setw(20) << "[word]" << "\t[frequency]\n\n";
	for (map<string, int>::iterator i = m.begin(); i != m.end(); ++i)
		cout << setiosflags(ios::left) << setw(20) << i->first << '\t' << i->second << endl;
}

	int main()
	{
		string s;
		cin >> s;
		char *p = new char[s.size() + 1];
		memset(p, 0, s.size() + 1);
		memcpy(p, s.c_str(), s.size());
		cout << "ÇëÊäÈëÒ»´®×Ö·û" << s << endl;
		statistic(p);
	}