**1.RSA加密**  
><br>**1.同余：**
>><br> &emsp;&emsp; $a \equiv b \pmod{m}$
>>><br>1.1 逆元：
>>><br> &emsp;&emsp; $a \times x \equiv 1 \pmod{m}$
>>>&emsp;&emsp;	$x \equiv a^{-1} \pmod{m}$&emsp;&emsp;则称x为a模m的逆元

><br>**2.RSA加密原理：**
>><br> n为模数&emsp;&emsp;e为公钥指数&emsp;&emsp;c为密文&emsp;&emsp;m为明文
>><br>​c ≡ m^e (mod n)

><br>**3.RSA解密原理:**
>><br>3.1 选择两个大质数 p和 q，并计算模数 n和欧拉函数 φ(n):
>><br>n = p × q
>><br>ψ(n) = (p-1) × (q-1)&emsp;&emsp;m^e ≡ C (mod n)&emsp;&emsp;c^d ≡ m (mod n)
>><br>m^(e×d) ≡ m (mod n)
>><br>3.2 其是依靠欧拉公式：
>><br>&emsp;&emsp;m^φ(n) ≡ 1 (mod n)
>><br>3.3 其后续可以变为：
>><br>&emsp;&emsp;m^(k × φ(n) + 1) ≡ m (mod n)
>><br>&emsp;&emsp;e×d = k×ψ(n)+1 ⇒ e×d ≡ 1 (mod ψ(n))
>><br>&emsp;&emsp;d = e^(-1) mod ψ(n)&emsp;&emsp;**or**&emsp;&emsp;d = pow(e, -1, ψ(n))
>><br>&emsp;&emsp;m = c^d mod(n)
<br>
<br>

**2.共享素数攻击**
><br>通过gcd（n1,n2) = 共享素数p
>><br>q1 = n1 // p&emsp;&rArr;\phi(n1) = (p-1)(q1-1)&emsp;&rArr;d1=e^(-1)mod\phi(n1)
>><br>q2 = n2 // p&emsp;&rArr;\phi(n2) = (p-1)(q2-1)&emsp;&rArr;d2=e^(-1)mod\phi(n2)
>><br>m1 = c^(d1)mod n1
