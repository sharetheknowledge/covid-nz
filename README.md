# covid-nz
Predict the evolution of covid-19 in NZ


The script in this folder tries to predict the number of infected people in NZ at a certain day from Day 1 - Day 1 being the first day of appearance of the virus in NZ.

The equation to be solved: x(t) =x0*b0^t        (1)

Tha main unknown to be found is 'b0' called the growth factor. 

Here, we try to find it via Linear Regression, i.e: y = a+b*x             (2)


So to fit equation (1) into equation (2) we are using the log(x) for equation (1):


log(x(t)) = log(x0*b0^t) = log(x0) + log(b0)*t

with log(x0)=a    and   
     log(b0)=b
     
 Taking the number of cases in NZ up until the 26/03/2020  (283 confirmed cases up until now), the result of the script attached gives:                                             
                                           a=log(x0)=-0.6546
                                           b=log(b0)=0.1977
                                           
                                           So x0=exp(a)=0.519649881
                                           and b0=exp(b)=1.21859676

So our formula for predicting the number of cases in NZ from day 1 (being the 28/02/2020) is:

x(t)=0.519649881*1.21859676^t

t being the number of days from the 28/02/2020


Source:https://towardsdatascience.com/modeling-exponential-growth-49a2b6f22e1f



