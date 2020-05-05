
Read a string word by word

```
#include <fstream>
#include <string>

int main()
{
    string t = "First Second Third";
    istringstream iss(t);
    string word;
    while(iss >> word) {
        /* do stuff with word */
        cout << word << endl;
    }
}
```

Output:
```
First
Second
Third
```


Splitting a string with a delimiter & storing all words in a vector

```
void split(const string& s, char delim,vector<string>& v) {
    auto i = 0;
    auto pos = s.find(delim);
    while (pos != string::npos) {
      v.push_back(s.substr(i, pos-i));
      i = ++pos;
      pos = s.find(delim, pos);

      if (pos == string::npos)
         v.push_back(s.substr(i, s.length()));
    }
}
```
