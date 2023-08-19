### Experiment No: 05
### Experiment Name: Study of Z-Transformation of Causal, Non-causal and Anti causal Signals
### Theory:
<p style="text-align: justify">
  
A *causal signal* refers to a type of signal that has a cause-and-effect relationship with another phenomenon. In other words, the occurrence or change of the signal directly influences or causes a corresponding change in another system or process. Causality is a fundamental concept in various fields, including physics, engineering, biology, and social sciences.
</p>
<p style="text-align: justify">
  
A *non-causal signal* is a type of signal that does not exhibit a direct cause-and-effect relationship with another phenomenon or system. In other words, the occurrence or behavior of the signal does not lead to a corresponding change in another system or process. Non-causal signals are often considered to be random or unrelated to any specific cause.
</p>

<p style="text-align: justify">
  
An *anti-causal signal* is a signal that appears to have a cause-and-effect relationship that is opposite to what is expected based on traditional causality. In other words, an anti-causal signal appears to "anticipate" or precede the cause, suggesting that its variations occur before the cause occurs.
</p>

## Code:
**Causal signal:**
```matlab
x = [1 2 3 4];
l = length(x);
X = 0;
z = sym('z');
for i = 0:l-1
    X = X + x(i+1)*z^(-i);
end
display(x)
disp('Z-transform of x:')
display(X)
```
**Non-causal**
```matlab
x = [1 2 3 4];
l = length(x);
X = 0;
z = sym('z');
for i = l-1:-1:0
    X = X + x(i+1)*z^(abs(i-(l-1)));
end
display(x)
disp('Z-transform of x:')
display(X)
```
**Anti-causal**
```matlab
x = [1 2 3 4 5 6];
z_val = 3; 
l = length(x);
Z = 0;
z = sym('z');
for i = z_val:-1:1
    Z = Z + x(i)*z^(abs(i-(z_val)));
end
for j = z_val+1:l
    Z = Z + x(j)*z^(-(j-z_val));
end
display(x)
disp('Z-transform of x:')
display(Z)
```
## Output:

**Causal signal:**

![Output](https://github.com/i-m-swachha/Digital-Signal-Processing-Sessional/blob/main/Pic/causal.png)

**Non signal:**

![Output](https://github.com/i-m-swachha/Digital-Signal-Processing-Sessional/blob/main/Pic/non-causal.png)

**Anti-causal**

![Output](https://github.com/i-m-swachha/Digital-Signal-Processing-Sessional/blob/main/Pic/anti-causal.png)
### Discussion & Conclusion:
In this experiment, we used causal, non causal and anti causal signal for z transform. The experiment was done successfully and expected output was found.
