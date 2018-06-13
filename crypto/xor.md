XOR [Crypro 75]
---------------------
>Все сообщения зашифрованы одним ключом, для каждого сообщения есть известный фрагмент текста  
text1 = hello???????????????????  
cipher1 = [9, 22, 8, 10, 8, 38, 24, 16, 42, 7, 23, 10, 19, 52, 11, 24, 53, 32, 3, 26, 24, 1, 9, 16]  
text2 = ?????weather????????????  
cipher2 = [11, 4, 12, 2, 56, 14, 16, 8, 1, 1, 19, 21, 41, 24, 10, 10, 25, 24, 23, 5, 6, 4, 11, 20]  
text3 = ????????????kerbeross???  
cipher3 = [6, 27, 18, 0, 30, 12, 23, 7, 31, 24, 1, 56, 29, 14, 16, 9, 15, 25, 13, 29, 25, 55, 14, 17]  
text4 = ?????????????????????bye  
cipher4 = [16, 6, 22, 10, 14, 18, 42, 15, 25, 8, 31, 56, 2, 14, 19, 52, 27, 15, 4, 27, 53, 10, 30, 16]  
flag = ????????????????????????  
cipher5 = [39, 63, 37, 33, 28, 1, 69, 27, 42, 0, 5, 56, 24, 91, 22, 52, 25, 88, 1, 27, 24, 91, 70, 8]  
Расшифруйте флаг  

Пример кода, для решения задания  

```c++
#include <iostream>
#include <string>
#include <vector>

using namespace std;

int main()
{
    vector <int> ax,bx,cx,dx,fx,flag;
    string a="hello",b="weather",c="kerbeross",d="bye";
    ax.push_back(9);
    ax.push_back(22);
    ax.push_back(8);
    ax.push_back(10);
    ax.push_back(8);
    ax.push_back(38);
    ax.push_back(24);
    ax.push_back(16);
    ax.push_back(42);
    ax.push_back(7);
    ax.push_back(23);
    ax.push_back(10);
    ax.push_back(19);
    ax.push_back(52);
    ax.push_back(11);
    ax.push_back(24);
    ax.push_back(53);
    ax.push_back(32);
    ax.push_back(3);
    ax.push_back(26);
    ax.push_back(24);
    ax.push_back(1);
    ax.push_back(9);
    ax.push_back(16);
    bx.push_back(11);
    bx.push_back(4);
    bx.push_back(12);
    bx.push_back(2);
    bx.push_back(56);
    bx.push_back(14);
    bx.push_back(16);
    bx.push_back(8);
    bx.push_back(1);
    bx.push_back(1);
    bx.push_back(19);
    bx.push_back(21);
    bx.push_back(41);
    bx.push_back(24);
    bx.push_back(10);
    bx.push_back(10);
    bx.push_back(25);
    bx.push_back(24);
    bx.push_back(23);
    bx.push_back(5);
    bx.push_back(6);
    bx.push_back(4);
    bx.push_back(11);
    bx.push_back(20);
    cx.push_back(6);
    cx.push_back(27);
    cx.push_back(18);
    cx.push_back(0);
    cx.push_back(30);
    cx.push_back(12);
    cx.push_back(23);
    cx.push_back(7);
    cx.push_back(31);
    cx.push_back(24);
    cx.push_back(1);
    cx.push_back(56);
    cx.push_back(29);
    cx.push_back(14);
    cx.push_back(16);
    cx.push_back(9);
    cx.push_back(15);
    cx.push_back(25);
    cx.push_back(13);
    cx.push_back(29);
    cx.push_back(25);
    cx.push_back(55);
    cx.push_back(14);
    cx.push_back(17);
    fx.push_back(39);
    fx.push_back(63);
    fx.push_back(37);
    fx.push_back(33);
    fx.push_back(28);
    fx.push_back(1);
    fx.push_back(69);
    fx.push_back(27);
    fx.push_back(42);
    fx.push_back(0);
    fx.push_back(5);
    fx.push_back(56);
    fx.push_back(24);
    fx.push_back(91);
    fx.push_back(22);
    fx.push_back(52);
    fx.push_back(25);
    fx.push_back(88);
    fx.push_back(1);
    fx.push_back(27);
    fx.push_back(24);
    fx.push_back(91);
    fx.push_back(70);
    fx.push_back(8);
    dx.push_back(16);
    dx.push_back(6);
    dx.push_back(22);
    dx.push_back(10);
    dx.push_back(14);
    dx.push_back(18);
    dx.push_back(42);
    dx.push_back(15);
    dx.push_back(25);
    dx.push_back(8);
    dx.push_back(31);
    dx.push_back(56);
    dx.push_back(2);
    dx.push_back(14);
    dx.push_back(19);
    dx.push_back(52);
    dx.push_back(27);
    dx.push_back(15);
    dx.push_back(14);
    dx.push_back(27);
    dx.push_back(53);
    dx.push_back(10);
    dx.push_back(30);
    dx.push_back(16);
    int j=0;
    for (int i=0;i<a.size();i++)
    {
        flag.push_back(a[i]^ax[j]);
        j++;
    }
    for (int i=0;i<b.size();i++)
    {
        flag.push_back(b[i]^bx[j]);
        j++;
    }
    for (int i=0;i<c.size();i++)
    {
        flag.push_back(c[i]^cx[j]);
        j++;
    }
    for (int i=0;i<d.size();i++)
    {
        flag.push_back(d[i]^dx[j]);
        j++;
    }
    vector <int> ans;
    for (int i=0;i<flag.size();i++)
    {
        ans.push_back(flag[i]^fx[i]);
    }
    for (int i=0;i<ans.size();i++) cout << (char)ans[i];
    cout << endl;
    for (int i=0;i<ans.size();i++) cout << (char)flag[i];
    cout << endl;
    for (int i=0;i<flag.size();i++) cout << (char) (cx[i]^flag[i]);
    return 0;
}
```


>```FLAG{x0r_is_n0t_s3cur3!}```
