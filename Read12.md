## Read: Class 12 ##

### Pandas ###

- Panda is a core package with additional feature from a variety of other packages
- is like Excel in Python
- uses tables called DataFrame and operates transformations on the data

- Fundamental difference between panda and NumPy:
    - NumPy DataFrame have one dtype for the entire array
    - Panda DataFrame have one dtype per column


            import numpy as np
            import pandas as pd


- Object Creation:

    - creating a Series passing a list of values
        s = pd.Series([1, 3, 5, np.nan, 6, 8])

            In [3]: s = pd.Series([1, 3, 5, np.nan, 6, 8])

            In [4]: s
            Out[4]: 
            0    1.0
            1    3.0
            2    5.0
            3    NaN
            4    6.0
            5    8.0
            dtype: float64

    - creating a DataFrame pass a Numpy array w/datetime index and labeled colums:
        dates = pd.date_range("20130101", periods = 6)


            In [5]: dates = pd.date_range("20130101", periods=6)


            In [6]: dates
            Out[6]: 
            DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04',
                        '2013-01-05', '2013-01-06'],
                        dtype='datetime64[ns]', freq='D')


            In [7]: df = pd.DataFrame(np.random.randn(6, 4), index=dates, columns=list("ABCD"))




            In [8]: df
            Out[8]: 
                       
                            A         B         C         D
            2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
            2013-01-02  1.212112 -0.173215  0.119209 -1.044236
            2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
            2013-01-04  0.721555 -0.706771 -1.039575  0.271860
            2013-01-05 -0.424972  0.567020  0.276232 -1.087401
            2013-01-06 -0.673690  0.113648 -1.478427  0.524988



- Viewing Data:
    - to view the top and bottome rows of the frame:


            In [13]: df.head()
            Out[13]: 


                            A         B         C         D
            2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
            2013-01-02  1.212112 -0.173215  0.119209 -1.044236
            2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
            2013-01-04  0.721555 -0.706771 -1.039575  0.271860
            2013-01-05 -0.424972  0.567020  0.276232 -1.087401


            In [14]: df.tail(3)
            Out[14]: 

                            A         B         C         D
            2013-01-04  0.721555 -0.706771 -1.039575  0.271860
            2013-01-05 -0.424972  0.567020  0.276232 -1.087401
            2013-01-06 -0.673690  0.113648 -1.478427  0.524988
            Display the index, columns:


            In [15]: df.index
            Out[15]: 


            DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04',
                        '2013-01-05', '2013-01-06'],
                        dtype='datetime64[ns]', freq='D')


            In [16]: df.columns
            Out[16]: Index(['A', 'B', 'C', 'D'], dtype='object')  


- show quick statistic summary
     df.describe()


            In [19]: df.describe()
            Out[19]: 

                        A         B         C         D
            count  6.000000  6.000000  6.000000  6.000000
            mean   0.073711 -0.431125 -0.687758 -0.233103
            std    0.843157  0.922818  0.779887  0.973118
            min   -0.861849 -2.104569 -1.509059 -1.135632
            25%   -0.611510 -0.600794 -1.368714 -1.076610
            50%    0.022070 -0.228039 -0.767252 -0.386188
            75%    0.658444  0.041933 -0.034326  0.461706
            max    1.212112  0.567020  0.276232  1.071804    


