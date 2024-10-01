# 2022년도 1학기 진화형 알고리즘 텀 프로젝트
2022년도 부산대학교 대학원 정보융합공학과 AI 전공 진화형 알고리즘 수업 텀 프로젝트입니다.

## 개요
In this assignment, you will experiment with some evolutionary algorithms to minimize a set of benchmark functions given below in Table 1.  

The first function $f_{1}$ is a high-dimensional unimodal function with only one peak in the search space. The functions $f_{2}$ and $f_{3}$ are high-dimensional multimodal functions with a lot of local optima. The function $f_{4}$ is a low-dimensional multimodal functions with only a few local optima. While the function $f_{1}$ – $f_{3}$ are scalable to any dimension, thirty-dimensional versions will be used in your experiments as indicated in column $D$ of Table 1. Since these are function optimization problems, it will be natural to adopt real number representations.  

The recommended genetic operators are simulated binary crossover (SBX) and polynomial mutation. You should carefully determine the values of hyper-parameters such as the crossover rate, mutation rate, and so on. The population size recommended is 100. The termination condition (i.e., the maximum number of evaluations) for each function should be determined by trial and error  

### Table 1. Benchmark functions to be tested in your experiments
| Name  | Function | $D$ | Domain  |
| ------------- | ------------- | ------------- | ------------- |
| Rosenbrock | $f_{1}(\textbf{x})=\sum^D_{i=1}[100(x_{i + 1}-x^2_{i})^2 + (1 - x_{i})^2]$ <br> $f(\textbf{x}^*)=0$, at $\textbf{x}^\ast =(1,\dots,1)$ | 30  | $[-30, 30]^D$  |
| Rastrigin | $f_{2}(\textbf{x})=10D+\sum^D_{i=1}\big(x^2_{i}-10\cos(2\pi\cdot x_{i})\big)$ <br>  $f(\textbf{x}^*)=0$, at $\textbf{x}^\ast=(0,\dots,0)$ | 30 | $[-5.12, 5.12]^D$  |
| Griewank  | $f_{3}(\textbf{x})=1+\sum^D_{i-1}x^2_{i}/4000-\prod^D_{i=1}\cos\big(x_{i}/\sqrt{i}\big)$ <br> $f(\textbf{x}^*)=0$, at $\textbf{x}^\ast=(0,\dots,0)$ | 30 | $[-600, 600]^D$  |
| Six-hump Camel  | $f_{4}(\textbf{x})=4x^2_{1}-2.1x^4_{1}+3^{-1}x^6_{1}+x_{1}x_{2}-4x^2_{2}+4x^4_{2}$ <br> $f(\textbf{x}^*)=-1.0316$, at $\textbf{x}^\ast=(0.0898, -0.7126)$ and $(-0.0898, 0.7126)$ | 2  | $[-5, 5]^D$  |  

### Experiments
1. Implement two different versions of a standard genetic algorithm with different selection schemes, one with stochastic uniform sampling (SUS) and the other with binary tournament selection, and then compare their performances.
2. Compare the performance of restricted tournament selection (RTS) algorithm with that of the winner algorithm chosen in Experiment 1. Conduct the above experiments separately for each of the test functions in Table 1, and see if the winners are different for different functions

## 세팅
* 구현 언어
    * Python, Jupyter Notebook
* 실험
    * 실험 1: SUS vs BTS
    * 실험 2: BTS vs RTS  

 Name  | Run | Generation |
| ------------- | ------------- | ------------- |
| Rosenbrock |20 | 5000  |
| Rastrigin | 20 | 5000 |
| Griewank  | 20 | 5000 |
| Six-hump Camel  | 20 | 10  |

## 실험 결과
### 실험 1.
#### 1.1 Rosenbrock

<div>
    <img src="img\experiment1\rosenbrock(complete)\rosenbrock_all_bsf_plot.png" width="55%">
    <img src="img\experiment1\rosenbrock(complete)\rosenbrock_sus_bsf_describe.png">
    <img src="img\experiment1\rosenbrock(complete)\rosenbrock_bts_bsf_describe.png">
</div>

#### 1.2 Rastrigin
<div>
    <img src="img\experiment1\rastrigin(complete)\rastrigin_all_bsf_plot.png" width="55%">
    <img src="img\experiment1\rastrigin(complete)\rastrigin_sus_bsf_describe.png">
    <img src="img\experiment1\rastrigin(complete)\rastrigin_bts_bsf_describe.png">
</div>

#### 1.3 Griewank
<div>
    <img src="img\experiment1\griewank(complete)\griewank_all_bsf_plot.png" width="55%">
    <img src="img\experiment1\griewank(complete)\griewank_sus_bsf_describe.png">
    <img src="img\experiment1\griewank(complete)\griewank_bts_bsf_describe.png">
</div>
    
#### 1.4 Six-Hump Camel
<div>
    <img src="img\experiment1\six-hump-camel(complete)\six-hump-camel_all_bsf_plot.png" width="55%">
    <img src="img\experiment1\six-hump-camel(complete)\six-hump-camel_sus_bsf_describe.png">
    <img src="img\experiment1\six-hump-camel(complete)\six-hump-camel_bts_bsf_describe.png">
</div>

### 실험 1. 전체 결과
 Name  | t-statistic | p-value | 유의성 | 성능 |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Rosenbrock |3.1183 | 0.0057 | ○ | BTS | 
| Rastrigin | 973…640.31 | 4.19767e-217 | ○ | BTS | 
| Griewank  | 255.8317 | 4.495064e-35 | ○ | BTS | 
| Six-hump Camel  | 1.1953 | 0.2467 | ☓  | BTS |

### 실험 2
#### 1.1 Rosenbrock
<div>
    <img src="img\experiment2\rosenbrock(complete)\rosenbrock_all_bsf_plot.png" width="55%">
    <img src="img\experiment2\rosenbrock(complete)\rosenbrock_bts_bsf_describe.png">
    <img src="img\experiment2\rosenbrock(complete)\rosenbrock_rts_bsf_describe.png">
</div>

#### 1.2 Rastrigin
<div>
    <img src="img\experiment2\rastrigin(complete)\rastrigin_all_bsf_plot.png" width="55%">
    <img src="img\experiment2\rastrigin(complete)\rastrigin_bts_bsf_describe.png">
    <img src="img\experiment2\rastrigin(complete)\rastrigin_rts_bsf_describe.png">
</div>

#### 1.3 Griewank
<div>
    <img src="img\experiment2\griewank(complete)\griewank_all_bsf_plot.png" width="55%">
    <img src="img\experiment2\griewank(complete)\griewank_bts_bsf_describe.png">
    <img src="img\experiment2\griewank(complete)\griewank_rts_bsf_describe.png">
</div>
    
#### 1.4 Six-Hump Camel
<div>
    <img src="img\experiment2\six-hump-camel(complete)\six-hump-camel_all_bsf_plot.png" width="55%">
    <img src="img\experiment2\six-hump-camel(complete)\six-hump-camel_bts_bsf_describe.png">
    <img src="img\experiment2\six-hump-camel(complete)\six-hump-camel_rts_bsf_describe.png">
</div>

### 실험 2. 전체 결과
 Name  | t-statistic | p-value | 유의성 | 성능 |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Rosenbrock | -7.5921 | 3.613611e-7 | ○ | BTS | 
| Rastrigin | -361…685.171 | 6.409476e-228 | ○ | BTS |
| Griewank  | -22.3373 | 4.232368e-15 | ○ | BTS |
| Six-hump Camel  | -11.6477 | 4.278509e-10 | ○ | BTS |

## 결론
* 전체적으로 binary tournament selection이 압도적인 성능적 우위를 보임
    * 다양성 보장력이 뛰어난 RTS가 멀티 모달 함수인 Rastrigin, Griewank, Six-hump Camel 함수 최적화에서 BTS보다 성능적으로 뛰어날 것으로 기대했으나, 그렇지 않았음
    * 이는 파라미터의 차이로 인해 RTS의 성능이 떨어진 것으로 예상됨
    * 추후 보완이 필요함
