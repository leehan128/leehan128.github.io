---
layout: post
comments : true
title: Strassen Algorithm
date : 2020-04-07 10:10:10
author: leehan
background: '/img/bg-post.jpg'
categories : Altorithm
tags : Algorithm, 대학 과제
---



# [Strassen Algorithm](https://m.blog.naver.com/PostView.nhn?blogId=babobigi&logNo=220502327816&proxyReferer=https:%2F%2Fwww.google.com%2F)

### 행렬의 곱셈

크기가 n * n인 두 행렬 **A**와 **B**의 곱을 **C**로 나타내고자 한다.

**A**의 원소를 ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgk9ri3338ptm.jpg%22&type=w2) 라 하고, ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkavqe24i89q.jpg%22&type=w2) 는 가로 ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkb607pg9oe3.jpg%22&type=w2) 는 세로를 나타낸다.

**B**와 **C**도 동일하게 표시한다.

<br/>

행렬의 곱셈을 다음과 같이 표현할 수 있다.

![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkdfr2qjsuqs.jpg%22&type=w2) 

**C** 하나의 원소를 구하는데 드는 비용은

곱셈 *n*번과 덧셈 *n-1* 번이다.

따라서, **C** 전체를 구할 경우 **C**의 크기는 n * n이므로

곱셈 ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkifggg728op.jpg%22&type=w2)번 그리고 덧셈을 ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkizvgb1657n.jpg%22&type=w2) 번 하게 된다.

<br/>

### 행렬의 곱셈 점화식

다음의 예는 n * n의 정사각 행렬의 크기가 ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgm25ktqv49bn.jpg%22&type=w2) 이다.

※![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgm25ktqv49bn.jpg%22&type=w2) 이 아닐 때는 가로세로에 0으로 채워진 가로세로 줄을 추가해서 ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgm25ktqv49bn.jpg%22&type=w2) 을 만들어준다. 절반씩 줄이기 때문에 2의 제곱승으로 만들어주는 거다.

![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgm9ch32b5ok9.jpg%22&type=w2) 

따라서, 행렬의 곱셈은 ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgmf37fnvhr1r.jpg%22&type=w2) 크기의 행렬을 8번 곱하고, ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgmf37fnvhr1r.jpg%22&type=w2) 크기의 행렬을 4번 더한다.

더하기를 생략하고, 점화식으로 나타낸다면

![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgmgqm0xq3q9u.jpg%22&type=w2)    

​             ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgmhhs7v0lkqc.jpg%22&type=w2)  

​             ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgmntt48gttax.jpg%22&type=w2) 

​              ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgmn8i9vjl964.jpg%22&type=w2) 

※ 점화식을 반복하면 8이 *log(n)*개가 생겨 *8^log(n)*이 된다.

이를 정리하면 *O(n^3)*이 된다는 걸 확인할 수 있다.

<br/>

### Strassen Algorithm(슈트라센 알고리즘)

1960년대 후반 슈트라센에 의해 제안된 ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkjounjhek20.jpg%22&type=w2) 보다 작은 알고리즘이다.

알고리즘의 내용은 다음과 같다.

![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgmttx5uq6pap.jpg%22&type=w2) 

위의 **P**부터 **V**를 가지고, 덧셈만으로 **A**와 **B** 행렬의 곱인 **C** 행렬을 찾을 수 있다.

![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgmve7rpku5qa.jpg%22&type=w2) 

<br/>

### Strassen Algorithm 점화식

두 행렬의 곱을 위의 R부터 V를 가지고 구한다면, ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgmf37fnvhr1r.jpg%22&type=w2) 크기의 행렬을 7번 곱하고

![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgmf37fnvhr1r.jpg%22&type=w2) 크기의 행렬을 18번 더한다. 더하기는 *O-Noatation*에 의해 생략되므로 곱하기만을 계산해본다.

![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgn49i0ovefhs.jpg%22&type=w2) 

​             ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgn4t6hcsos40.jpg%22&type=w2) 

​             ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgmntt48gttax.jpg%22&type=w2) 

​             ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgn5g6l0g03ie.jpg%22&type=w2) 

즉, 알고리즘의 성능은 ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgnj7vpdn8pdg.jpg%22&type=w2) 이다.

<br/>

<br/>

### C++ 행렬 곱셉 알고리즘!

아주 간단하게 C++ 언어로 행렬 곱셈을 구현해보자!

~~~c++
#include <iostream>

int main()
{
    int A[2][2] = {%raw%}{{1,2}, {3,4}}{%endraw%};
    int B[2][2] = {%raw%}{{1,2}, {3,4}}{%endraw%};
    int C[2][2];
    int i,j;
    
    std::cout << "행렬의 곱 : " << std::endl;
    for(i=0; i<2; i++)
    {
        for(j=0; j<2; j++)
        {
            C[i][j] = A[i][0]*B[0][j] + A[i][1]*B[1][j];
        }
    }
    
    for(i=0; i<2; i++)
    {
        for(j=0; j<2; j++)
        {
            std::cout << C[i][j] << " ";
        }
        std::cout << std::endl;
    }
    
    return 0;
}
~~~

2*2 행렬인 A와 B의 곱을 구해보았다. 우리집 컴퓨터를 기준으로 실행시간은 **0.05401초** 걸렸다.

이 다음은 슈트라센 알고리즘을 직접 구현해 볼 생각이다. 위에서 미리 값을 주고 간단하게 곱셈만 실행한 만큼 공정한 비교를 위해 아래에서도 비교적 간략하게 구현해볼 생각이다.

~~~c++
#include <iostream>

int main()
{
    int A[2][2] = {%raw%}{{1,2}, {3,4}}{%endraw%};
    int B[2][2] = {%raw%}{{1,2}, {3,4}}{%endraw%};
    int C[2][2];
    int i,j;
    
    int P,Q,R,S,T,U,V;
    P = (A[0][0] + A[1][1])*(B[0][0]+B[1][1]);
    Q = (A[1][0]+A[1][1])*B[0][0];
    R = A[0][0]*(B[0][1]-B[1][1]);
    S = A[1][1]*(B[1][0]-B[0][0]);
    T = (A[0][0]+A[0][1])*B[1][1];
    U = (A[1][0]-A[0][0])*(B[0][0]+B[0][1]);
    V = (A[0][1]-A[1][1])*(B[1][0]+B[1][1]);
    
    C[0][0] = P + S - T + V;
    C[0][1] = R + T;
    C[1][0] = Q + S;
    C[1][1] = P+R-Q+U;
    
    for(i=0; i<2; i++)
    {
        for(j=0; j<2; j++)
        {
            std::cout << C[i][j] << " ";
        }
        std::cout << std::endl;
    }
    
    return 0;
}
~~~

이렇게 간략하게 슈트라센 알고리즘의 동작을 구현해보았다. 우리집 컴퓨터를 기준으로 실행시간은 **0.0466초**가 나왔다. 확실히 위와 같은 결과값이지만 조금 더 실행시간이 단축되었음을 확인할 수 있다.

슈트라센 알고리즘은 시간복잡도는 ![](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgnj7vpdn8pdg.jpg%22&type=w2) 로 감소시켰지만 여기서 더 감소시키는 것도 가능하다. 현재 최고 기록은 ***Coppersmith-Winograd altorithm***인데 **O(n^2.373)**의 시간복잡도를 선보였다고 한다. 다만 구현이 복잡하고 수치 안정성이 떨어져 일반적으로 쓸만한 알고리즘은 슈트라센까지가 상한선인 것 같다.

