# Use Multi-phase Evolution Strategies Alogorthm to Solve Hedge Problem

## Brief Introduction 
Suppose Germany ’s revenue forecast for 2009 is 645 million marks (DM) and UK revenue forecast is 272 million pounds (BP). However, at the end of 2008, the exchange rate of the end of 2009 is not known. Therefore, I have simulated 1000 sets of possible Exchange Rate Changes, please refer to [SimExRates.csv](SimExRates.csv).

Our task is to target the respective call options of the two currencies, DM and BP, as shown in the below.
<p align = "center">
    <img src="./images/call options.PNG" width="50%">
</p>

Assuming that both currencies have a budget of 500 million, find out the combination of put options, and make Hedged Revenue achieve the following goals when it exchanges USD in 2009.
* Maximize expected income
* Minimize the chance of "revenue less than USD $ 706 million"

The decision variables for DM and BP are nine real numbers from 0 to 1, and the sum of the nine variables must be 1. There are a total of 18 decision variables.

## Pseudo-Code
```python 
Pop_size
Kid_size 
Max_generation 
Max_phase 
Next_phase_ratio 

while phase <= max_phase
    if phase == 1
        for k in Pop_size 
            m = Function A
            add m in MATRIX
    else
        MATRIX = Function D(NEXT_GEN_PARENT_MATRIX)
    while gen <= Max_generation
        KID_MATRIX = Function B(MATRIX)
        NEXT_GEN_PARENT_MATRIX, best_solution, best_profit = Function C(KID_MATRIX)
        MATRIX = NEXT_GEN_PARENT_MATRIX
        gen = gen + 1 
    phase = phase + 1 
```
## To Reproduce
I had posted the entire codes for two goals mentioned above.
* [Maximize expected income](Maximize-expected-income.ipynb)
* [Minimize the chance](Minimize-the-chance.ipynb)


1. Please download both of the codes
2. Upload both codes to Google Colab
3. Run them 

## Reference Paper
[Link](https://www.sciencedirect.com/science/article/abs/pii/S0377221710003115)
<p align = "center">
    <img src="./images/Reference Paper 1.jpg" width="70%">
</p>

<p align = "center">
    <img src="./images/Reference Paper 2.jpg" width="80%">
</p>

