### C02While.java

### 구구단

#### 1 - 9단 출력
```java
		int dan = 1;      // 시작 단 수 결정
		
		while(dan<10) {   // 9단까지 반복
			
			int i=1;        // 곱할 수 (ex. 2xi) 
			while(i<10) {   // x9까지 반복
				System.out.printf("%d x %d = %d\n", dan,i,dan*i);
				i++;
			}
			
			System.out.println();
			dan++;
		}
```

#### n - 9단 출력
```java
		Scanner sc = new Scanner(System.in); 
		int dan = sc.nextInt(); // 입력 받아와 함수에 넣기

		while(dan<10) {
			
			int i=1;
			while(i<10) {
				System.out.printf("%d x %d = %d\n", dan,i,dan*i);
				i++;
			}
			
			System.out.println();
			dan++;
		}
		sc.close();
```

#### n - m단 출력
```java
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt(); 
		int m = sc.nextInt();
		
		//유효성검증. (N<M, N>=2 && N<=9, M>2 && M<10) 이 아닌 경우
		while((n>=m) ||  (n<2 || n>9) || (m<=2 || m>=10)) {
			System.out.print("n,m 다시 입력 : ");
			n = sc.nextInt();
			m = sc.nextInt();
		}
		
		int dan = n;
		while(dan<(m+1)) { // m단이 될 때까지 반복
			
			int i=1;
			while(i<10) {
				System.out.printf("%d x %d = %d\n", dan,i,dan*i);
				i++;
			}
			
			System.out.println();
			dan++;
		}
		sc.close();
```

#### n - m단 반전 출력
```java
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int m = sc.nextInt();
		
		//유효성검증(N<M, N>=2 && N<=9, M>2 && M<10) 이 아닌 경우
		while((n>=m) ||  (n<2 || n>9) || (m<=2 || m>=10)) {
			System.out.print("n,m 다시 입력 : ");
			n = sc.nextInt();
			m = sc.nextInt();
		}
		
		int dan = m;
		while(dan>n-1) {
			
			int i=9;
			while(i>0) {
				System.out.printf("%d x %d = %d\n", dan,i,dan*i);
				i--;
			}
			
			System.out.println();
			dan--;
		}
		sc.close();
```

#### 1 - 9단 가로 출력 (개인학습)
```java
    int i = 1;
    int n = 2;
    
    while (i<= 9) {    // 세로 9번 반복, 곱해지는 수   
        n = 2; // 새 행 시작 시 2단으로 초기화
        while (n<=9) { // 가로 9번 반복, 단 변화 
            System.out.printf("%d x %d = %-2d \t", n, i, n*i);    
            n++; // 2~9단까지 옆으로 반복
        }
        System.out.println(); 
        i++; // x1~9까지 반복
    }
```

---

### 별찍기

#### 고정높이 별
```java
// *****
// *****
// *****
// *****

    int i=0;
    while(i<4) {
        
        int j=0;
        while(j<5) {
            System.out.print("*");
            j++;
        }
        System.out.println();
        i++;
    }
```
