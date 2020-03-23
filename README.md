# multi-annotation-parser
A dependency parser for multi-annotation data

## 实验结果
<table>
  <tr>
    <th>批次</th>
    <th colspan="2">结果</th>
    <th>ctb</th>
    <th>hit</th>
    <th>pmt</th>
	</tr >
	<tr >
    <td rowspan="4">从正确答案训练</td>
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>66.77%</td>
    <td>69.91%</td>
    <td>51.27%</td>
	</tr>
  <tr>
    <td>LAS</td>
    <td>62.22%</td>
    <td>63.78%</td>
    <td>42.33%</td>
	</tr>
	<tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>66.43%</td>
    <td>68.22%</td>
    <td>50.91%</td>
	</tr>
	<tr>
    <td>LAS</td>
    <td>60.85%</td>
    <td>62.13%</td>
    <td>40.27%</td>
	</tr>
  
  <tr >
    <td rowspan="4">以双人标注一致的数据训练，直接忽略双人不一致的数据</td>
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>66.01%</td>
    <td>69.29%</td>
    <td>47.86%</td>
	</tr>
  <tr>
    <td>LAS</td>
    <td>60.98%</td>
    <td>62.74%</td>
    <td>38.58%</td>
	</tr>
	<tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>65.50%</td>
    <td>68.01%</td>
    <td>47.81%</td>
	</tr>
	<tr>
    <td>LAS</td>
    <td>59.64%</td>
    <td>61.51%</td>
    <td>37.32%</td>
	</tr>
  
  <tr >
    <td rowspan="4">将双人标注不一致的句子看做两个独立的句子训练</td>
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>67.44%</td>
    <td>68.95%</td>
    <td>50.96%</td>
	</tr>
  <tr>
    <td>LAS</td>
    <td>62.66%</td>
    <td>62.39%</td>
    <td>41.12%</td>
	</tr>
	<tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>66.51%</td>
    <td>67.96%</td>
    <td>49.51%</td>
	</tr>
	<tr>
    <td>LAS</td>
    <td>61.13%</td>
    <td>61.71%</td>
    <td>38.83%</td>
	</tr>
  
  <tr >
    <td rowspan="4">将双人标注不一致的答案各赋予0.5的权重参与计算loss</td>
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>67.07%</td>
    <td>69.07%</td>
    <td>51.02%</td>
	</tr>
  <tr>
    <td>LAS</td>
    <td>61.70%</td>
    <td>52.66%</td>
    <td>40.89%</td>
	</tr>
	<tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>66.13%</td>
    <td>68.87%</td>
    <td>50.49%</td>
	</tr>
	<tr>
    <td>LAS</td>
    <td>60.89%</td>
    <td>52.36%</td>
    <td>39.61%</td>
	</tr>
  
   <tr >
    <td rowspan="4">将双人标注不一致的答案以或的关系参与计算loss</td>
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>65.33%</td>
    <td>69.87%</td>
    <td>50.96%</td>
	</tr>
  <tr>
    <td>LAS</td>
    <td>60.13%</td>
    <td>53.03%</td>
    <td>41.00%</td>
	</tr>
	<tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>65.59%</td>
    <td>68.89%</td>
    <td>50.63%</td>
	</tr>
	<tr>
    <td>LAS</td>
    <td>60.40%</td>
    <td>51.91%</td>
    <td>39.57%</td>
	</tr>
</table>
