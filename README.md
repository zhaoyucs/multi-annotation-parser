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
    <th>pmt2020重标</th>
  </tr >
  <tr >
    <td rowspan="6">从正确答案训练</td>
    <td rowspan="2">train</td>
    <td>UAS</td>
    <td>100%</td>
    <td>99.93%</td>
    <td>99.93%</td>
    <td>100%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>100%</td>
    <td>99.87%</td>
    <td>99.89%</td>
    <td>99.99%</td>
  </tr>
  <tr >
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>66.77%</td>
    <td>69.91%</td>
    <td>51.27%</td>
    <td>57.40%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>62.22%</td>
    <td>63.78%</td>
    <td>42.33%</td>
    <td>48.36%</td>
  </tr>
  <tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>66.43%</td>
    <td>68.22%</td>
    <td>50.91%</td>
    <td>58.39%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>60.85%</td>
    <td>62.13%</td>
    <td>40.27%</td>
    <td>49.26%</td>
  </tr>
  <tr >
    <td rowspan="6">以双人标注一致的数据训练，直接忽略双人不一致的数据</td>
    <td rowspan="2">train</td>
    <td>UAS</td>
    <td>100%</td>
    <td>99.97%</td>
    <td>99.98%</td>
    <td>100%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>100%</td>
    <td>99.97%</td>
    <td>99.96%</td>
    <td>99.99%</td>
  </tr>
  <tr >
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>66.01%</td>
    <td>69.29%</td>
    <td>47.86%</td>
    <td>55.29%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>60.98%</td>
    <td>62.74%</td>
    <td>38.58%</td>
    <td>44.71%</td>
  </tr>
  <tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>65.50%</td>
    <td>68.01%</td>
    <td>47.81%</td>
    <td>53.89%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>59.64%</td>
    <td>61.51%</td>
    <td>37.32%</td>
    <td>44.48%</td>
  </tr>
   <tr >
    <td rowspan="6">将双人标注不一致的句子看做两个独立的句子训练</td>
    <td rowspan="2">train</td>
    <td>UAS</td>
    <td>87.81%</td>
    <td>88.46%</td>
    <td>80.91%</td>
    <td>80.45%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>85.02%</td>
    <td>84.93%</td>
    <td>75.09%</td>
    <td>74.40%</td>
  </tr>
  <tr >
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>67.44%</td>
    <td>68.95%</td>
    <td>50.96%</td>
    <td>53.67%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>62.66%</td>
    <td>62.39%</td>
    <td>41.12%</td>
    <td>41.58%</td>
  </tr>
  <tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>66.51%</td>
    <td>67.96%</td>
    <td>49.51%</td>
    <td>53.07%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>61.13%</td>
    <td>61.71%</td>
    <td>38.83%</td>
    <td>41.89%</td>
  </tr>
   <tr >
    <td rowspan="6">(方法a)将双人标注不一致的答案各赋予0.5的权重参与计算loss</td>
    <td rowspan="2">train</td>
    <td>UAS</td>
    <td>89.57%</td>
    <td>88.69%</td>
    <td>79.53%</td>
    <td>73.84%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>87.22%</td>
    <td>71.44%</td>
    <td>72.96%</td>
    <td>66.27%</td>
  </tr>
  <tr >
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>67.07%</td>
    <td>69.07%</td>
    <td>51.02%</td>
    <td>53.31%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>61.70%</td>
    <td>52.66%</td>
    <td>40.89%</td>
    <td>41.14%</td>
  </tr>
  <tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>66.13%</td>
    <td>68.87%</td>
    <td>50.49%</td>
    <td>52.81%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>60.89%</td>
    <td>52.36%</td>
    <td>39.61%</td>
    <td>41.29%</td>
  </tr>
   <tr >
    <td rowspan="6">（方法b）将双人标注不一致的答案以或的关系（联合标签）参与计算loss</td>
    <td rowspan="2">train</td>
    <td>UAS</td>
    <td>90.85%</td>
    <td>91.20%</td>
    <td>81.91%</td>
    <td>74.62%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>88.60%</td>
    <td>71.79%</td>
    <td>75.37%</td>
    <td>65.96%</td>
  </tr>
  <tr >
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>65.33%</td>
    <td>69.87%</td>
    <td>50.96%</td>
    <td>52.41%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>60.13%</td>
    <td>53.03%</td>
    <td>41.00%</td>
    <td>41.62%</td>
  </tr>
  <tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>65.59%</td>
    <td>68.89%</td>
    <td>50.63%</td>
    <td>54.50%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>60.40%</td>
    <td>51.91%</td>
    <td>39.57%</td>
    <td>43.13%</td>
  </tr>
   <tr >
    <td rowspan="6">以相互一致率为权重，加权计算（方法a）</td>
    <td rowspan="2">train</td>
    <td>UAS</td>
    <td>89.94%</td>
    <td>89.00%</td>
    <td>80.53%</td>
    <td>73.86%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>87.25%</td>
    <td>85.11%</td>
    <td>74.31%</td>
    <td>65.05%</td>
  </tr>
  <tr >
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>67.74%</td>
    <td>70.05%</td>
    <td>52.14%</td>
    <td>52.90%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>62.72%</td>
    <td>64.09%</td>
    <td>42.33%</td>
    <td>40.28%</td>
  </tr>
  <tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>66.92%</td>
    <td>68.27%</td>
    <td>50.24%</td>
    <td>52.83%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>61.47%</td>
    <td>62.04%</td>
    <td>39.91%</td>
    <td>41.13%</td>
  </tr>
   <tr >
    <td rowspan="6">以相互一致率为权重，加权计算（方法b）</td>
    <td rowspan="2">train</td>
    <td>UAS</td>
    <td>91.22%</td>
    <td>91.27%</td>
    <td>82.20%</td>
    <td>74.87%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>88.52%</td>
    <td>88.05%</td>
    <td>75.68%</td>
    <td>66.46%</td>
  </tr>
  <tr >
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>67.15%</td>
    <td>69.83%</td>
    <td>51.04%</td>
    <td>53.35%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>62.22%</td>
    <td>63.58%</td>
    <td>40.78%</td>
    <td>41.46%</td>
  </tr>
  <tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>66.78%</td>
    <td>68.78%</td>
    <td>49.77%</td>
    <td>54.44%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>61.34%</td>
    <td>62.53%</td>
    <td>39.39%</td>
    <td>43.72%</td>
  </tr>
   <tr >
    <td rowspan="6">以相互一致率为权重，加权计算（方法b）,同时加权label</td>
    <td rowspan="2">train</td>
    <td>UAS</td>
    <td>91.22%</td>
    <td>91.32%</td>
    <td>80.98%</td>
    <td>74.67%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>89.21%</td>
    <td>88.54%</td>
    <td>74.41%</td>
    <td>66.59%</td>
  </tr>
  <tr >
    <td rowspan="2">dev</td>
    <td>UAS</td>
    <td>67.82%</td>
    <td>70.01%</td>
    <td>50.68%</td>
    <td>51.85%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>62.70%</td>
    <td>63.88%</td>
    <td>40.38%</td>
    <td>40.57%</td>
  </tr>
  <tr>
    <td rowspan="2">test</td>
    <td>UAS</td>
    <td>66.63%</td>
    <td>68.44%</td>
    <td>49.91%</td>
    <td>52.37%</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>60.98%</td>
    <td>62.18%</td>
    <td>39.21%</td>
    <td>41.47%</td>
  </tr>
</table>
