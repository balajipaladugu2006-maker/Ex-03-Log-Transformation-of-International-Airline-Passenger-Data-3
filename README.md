
## NAME : Paladugu Venkata Balaji
## REG NO: 2305001024
## Aim
To perform log transformation on the International Airline Passenger dataset using Python.

## Objectives
1. To load the airline passenger dataset.
2. To visualize the original time series data.
3. To apply log transformation using NumPy.
4. To compare the original and transformed time series.
5. To analyze variance before and after transformation.
## Program
~~~python

    import pandas as pd
    import numpy as np
    import matplotlib.pyplot as plt
    df = pd.read_csv("AirPassengers.csv")
    df["Month"] = pd.to_datetime(df["Month"])
    df.set_index("Month", inplace=True)
    print("Original Data:")
    print(df.head())
    plt.figure(figsize=(10, 5))
    plt.plot(df.index, df["Passengers"])
    plt.title("International Airline Passengers")
    plt.xlabel("Year")
    plt.ylabel("Passengers")
    plt.grid(True)
    plt.show()
    df["Log_Passengers"] = np.log(df["Passengers"])
    print("Log Transformed Data:")
    print(df.head())
    plt.figure(figsize=(10, 5))
    plt.plot(df.index, df["Log_Passengers"])
    plt.title("Log-Transformed Airline Passenger Data")
    plt.xlabel("Year")
    plt.ylabel("Log(Passengers)")
    plt.grid(True)
    plt.show()
    fig, axes = plt.subplots(2, 1, figsize=(10, 8))
    axes[0].plot(df.index, df["Passengers"])
    axes[0].set_title("Original Time Series")
    axes[0].grid(True)
    axes[1].plot(df.index, df["Log_Passengers"])
    axes[1].set_title("Log-Transformed Time Series")
    axes[1].grid(True)
    plt.tight_layout()
    plt.show()
    print("Variance Before Transformation:", df["Passengers"].var())
    print("Variance After Transformation:", df["Log_Passengers"].var())
 ~~~
 ## Output

 <img width="705" height="521" alt="image" src="https://github.com/user-attachments/assets/4baa1447-d072-4b94-9f7b-6e038c640d48" />
 <img width="1246" height="573" alt="image" src="https://github.com/user-attachments/assets/502e33ad-8ede-425c-a053-d1b267a7cac5" />
 <img width="530" height="237" alt="image" src="https://github.com/user-attachments/assets/43aa76b0-a91c-47ac-96ae-2fe94786c879" />
 <img width="1245" height="562" alt="image" src="https://github.com/user-attachments/assets/6717bdef-3956-40c3-919a-ba23f048e509" />
 <img width="1063" height="778" alt="image" src="https://github.com/user-attachments/assets/01b470f1-61a4-4c40-b1e2-7fcabe8cf876" />

## Result
Log transformation was successfully applied to the International Airline Passenger dataset. The original and transformed series were plotted and compared. The transformation compresses larger values and may help stabilize increasing variability.
