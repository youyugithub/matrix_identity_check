# matrix_identity_check
matrix identity check

```
set.seed(0)
n<-10
p<-5
Sigmab<-rWishart(1,20,diag(p))[,,1]
Sigmae<-rWishart(1,20,diag(n))[,,1]
XX<-matrix(rnorm(n*p)*5,n,p)

mub<-rnorm(p)*5
yy<-rnorm(n)*5

mub+solve(solve(Sigmab)+t(XX)%*%solve(Sigmae)%*%XX)%*%t(XX)%*%solve(Sigmae)%*%(yy-XX%*%mub)
mub+Sigmab%*%t(XX)%*%solve(XX%*%Sigmab%*%t(XX)+Sigmae)%*%(yy-XX%*%mub)
```
