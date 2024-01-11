# Basics

***breaking queries and injecting sql***  
**"#" is statement terminator for MySQL.  
This depends on distributions of SQL**  
![172ff6900f6cb463b919d599b4ce5876.png](../_resources/172ff6900f6cb463b919d599b4ce5876.png)

![df390e6d7deef8a3b8f7ae764a65a94f.png](../_resources/df390e6d7deef8a3b8f7ae764a65a94f.png)

**Getting version**  
![70b9e9d60952db906f1c15c1861547f3.png](../_resources/70b9e9d60952db906f1c15c1861547f3.png)

**Extracting table names**  
![983c6b0c742dffe7bc9020a36bc23278.png](../_resources/983c6b0c742dffe7bc9020a36bc23278.png)

![ef85b11a68697a455c33fa9bee50fd6b.png](../_resources/ef85b11a68697a455c33fa9bee50fd6b.png)

![dfb21842dd3b116c3d6775d6f1737da2.png](../_resources/dfb21842dd3b116c3d6775d6f1737da2.png)

***Resource:*** https://portswigger.net/web-security/sql-injection/cheat-sheet

# Using tools to check sql injection

## SQLmap

Request file:  
![7b7506d26d5aa28b9311743f9c5fc696.png](../_resources/7b7506d26d5aa28b9311743f9c5fc696.png)  
![4a6b5d6883a0c9348a833719dcdea738.png](../_resources/4a6b5d6883a0c9348a833719dcdea738.png)  
![af277e9e7ef6bf7c9b8c03d0ce5eb40f.png](../_resources/af277e9e7ef6bf7c9b8c03d0ce5eb40f.png)

**Checking headers content for injection**  
![f515419e206a01311dfd8ffcd5565cd3.png](../_resources/f515419e206a01311dfd8ffcd5565cd3.png)

**Asking true/false questions with request and enumerating info**  
*Here sql version:*  
Invalid content-length = 1928  
Valid = 1027  
![9aa6f800f5b9e09c1dc6d20f0cf0973f.png](../_resources/9aa6f800f5b9e09c1dc6d20f0cf0973f.png)

- Valids  
    ![97801034c72f14c65546de6c5f056673.png](../_resources/97801034c72f14c65546de6c5f056673.png)  
    ![eaab10ca292c498b06e3435554791a6a.png](../_resources/eaab10ca292c498b06e3435554791a6a.png)  
    ![941cd2d5bf9965aba26ef9a8be9047c0.png](../_resources/941cd2d5bf9965aba26ef9a8be9047c0.png)

*Extracting password*  
![6827e561bfd86becdc31b94207a60d68.png](../_resources/6827e561bfd86becdc31b94207a60d68.png)

Sending in intruder and attacking it.  
![b4f325a9edc7be50633b3f4665dbc4b8.png](../_resources/b4f325a9edc7be50633b3f4665dbc4b8.png)  
![f9194ca37244c914d827baabc33bc5cb.png](../_resources/f9194ca37244c914d827baabc33bc5cb.png)

*Using sqlmap*  
![10d9658ba910ffa759285bbb27bb3eed.png](../_resources/10d9658ba910ffa759285bbb27bb3eed.png)  
![30aaddf41edfa20130625d30267e5628.png](../_resources/30aaddf41edfa20130625d30267e5628.png)  
![e3f3cdfa74b6b41575dacaf3f0bb7025.png](../_resources/e3f3cdfa74b6b41575dacaf3f0bb7025.png)

- dumping all tables data  
    ![3933869eb3aa4fc4280c84a5af5ce525.png](../_resources/3933869eb3aa4fc4280c84a5af5ce525.png)
    
- dumping specific table![b7ba91929879510c855e25e7c26cd797.png](../_resources/b7ba91929879510c855e25e7c26cd797.png)  
    ![12c04c5b9463c7e3f1a48cf7b38ff6e8.png](../_resources/12c04c5b9463c7e3f1a48cf7b38ff6e8.png)
    

# Challenge Lab 3
- Product parameter is sql injectable
**Union select:**
![8b2d5345028a694aa05a38d03cc7ad7e.png](../_resources/8b2d5345028a694aa05a38d03cc7ad7e.png)
**Getting table names**
![d020d0e633f9c46102b7a8179d0a8381.png](../_resources/d020d0e633f9c46102b7a8179d0a8381.png)
![071d4404fe0cc1736066e98821996893.png](../_resources/071d4404fe0cc1736066e98821996893.png)

***Use sqlmap to dump all data***
![90705e138b979a0e82dff70a57500442.png](../_resources/90705e138b979a0e82dff70a57500442.png)

![4963ba2bd62375c1f2fb4e50d085c6ea.png](../_resources/4963ba2bd62375c1f2fb4e50d085c6ea.png)
![6c3d6c264950e7fc68a7910f15826036.png](../_resources/6c3d6c264950e7fc68a7910f15826036.png)
![1d3a095a44c91c42c7783177869c1f1d.png](../_resources/1d3a095a44c91c42c7783177869c1f1d.png)

# Second order sql injection
- Basically, if there is any input field from any sort of page like register, etc which is being rendered later on then you can try entering sql injection payloads to later on see if application is sql injectable or not.

**Normal username payload account**
![f7d3495533832408c8e70ae5a355dfbd.png](../_resources/f7d3495533832408c8e70ae5a355dfbd.png)
No bio.

**SQL Injected username payload**
![7dc65f6784bf7f796d69c02dd86276de.png](../_resources/7dc65f6784bf7f796d69c02dd86276de.png)
![4aec671150dd8ec39e0b788a3471b38a.png](../_resources/4aec671150dd8ec39e0b788a3471b38a.png)
Got bio from injected payload.

https://book.hacktricks.xyz/pentesting-web/sql-injection/sqlmap/second-order-injection-sqlmap
![b63ecbdac613277183bf785ed9edb311.png](../_resources/b63ecbdac613277183bf785ed9edb311.png)



