# Wafer Heatmap Visualization

Heatmap sometime could be extremely useful, you can gain intuitive insight from the plot which contains   information on both location and distribution, and manage to find potential pattern behind it. 

This package is implemented on the top of _seaborn_, and further customized by _matplotlib_. It provides an easy way to visualize wafer map data, both numerical and categorical data are supported.

Before you start, you should have some knowledge on _pandas_ and transform your data into `pd.DataFrame`, then make sure that positional data (x/row,y/col)  are included in separate columns and encoded as integer.




## Installation


To install wfmap via PyPI using pip:

```bash
pip install wfmap
```
or build the latest release from Github:

```bash
git clone https://github.com/xlhaw/wfmap.git
cd wfmap
python setup.py install
```



## Basic Usage

For demonstration, I generate some dummy data under the `/data` folder. Let's load the data at first and explore the usage of this package.

```python
import pandas as pd
from wfmap import wafermap
data=pd.read_csv('/data/demo.csv')
```

To better understand the data, take the first entry for example, it suggests that the _Die#0_ which located at `#11 ` row and `#60` col in wafer map, is `OK`  defined by _Defect Code_  and its _Metrics_ is `84.3`.



**Numerical Data**

'MAP_ROW' and 'MAP_COL' are the default column name for wafer mapping.  If you have preprocessed your data as the same format as I did above. The command required could be as simple as follows:

```python
wafermap(data,value='DATA',dtype='num')
```

![DATA](/img/Figure_2.png)[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fxlhaw%2Fwfmap.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fxlhaw%2Fwfmap?ref=badge_shield)


On the left side of  heatmap is the horizontal histogram plot of `DATA`, with colorized y-axis and invisible x-axis for visual aesthetics.



**Categorical Data **

Similar to above numerical/continuous data, categorical data such as _Defect Code_ `CODE` can also be visualized as below.

```python
wafermap(data,value='CODE',dtype='cat')
```

![CODE](/img/Figure_1.png)

In addition to the regular heatmap, I put the histogram subplot and pie chart inset on the right half. For the sake of simplicity, only the ratio of  top 5 categories will be annotated. 

 








## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fxlhaw%2Fwfmap.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fxlhaw%2Fwfmap?ref=badge_large)