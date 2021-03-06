# π μμνκΈ°

## μ€μΉνκΈ°

TOAST UI μ νλ€μ ν¨ν€μ§ λ§€λμ λ₯Ό μ΄μ©νκ±°λ, μ§μ  μμ€ μ½λλ₯Ό λ€μ΄λ°μ μ¬μ©ν  μ μλ€. νμ§λ§ ν¨ν€μ§ λ§€λμ  μ¬μ©μ κΆμ₯νλ€.

### ν¨ν€μ§ λ§€λμ  μ¬μ©νκΈ°

TOAST UI μ νλ€μ [npm](https://www.npmjs.com/) ν¨ν€μ§ λ§€λμ μ λ±λ‘λμ΄ μλ€.
κ° ν¨ν€μ§ λ§€λμ κ° μ κ³΅νλ CLI λκ΅¬λ₯Ό μ¬μ©νλ©΄ μ½κ² ν¨ν€μ§λ₯Ό μ€μΉν  μ μλ€. npm μ¬μ©μ μν΄μ  [Node.js](https://nodejs.org)λ₯Ό λ―Έλ¦¬ μ€μΉν΄μΌ νλ€.

#### npm

```sh
$ npm install --save @toast-ui/chart # μ΅μ  λ²μ 
$ npm install --save @toast-ui/chart@<version> # νΉμ  λ²μ 
```

### Contents Delivery Network (CDN) μ¬μ©νκΈ°

TOAST UI Chartλ CDNμ ν΅ν΄ μ¬μ©ν  μ μλ€.

- μλμ μ½λλ‘ CDNμ μ¬μ©ν  μ μλ€.

```html
<link rel="stylesheet" href="https://uicdn.toast.com/chart/latest/toastui-chart.min.css" />
<script src="https://uicdn.toast.com/chart/latest/toastui-chart.min.js"></script>
```

- CDNμ μλμ λλ ν λ¦¬ κ΅¬μ‘°λ‘ κ΅¬μ±λμ΄ μλ€.

```
- uicdn.toast.com/
  ββ chart/
  β  ββ latest
  β  β  ββ toastui-chart.js
  β  β  ββ toastui-chart.min.js
  β  β  ββ toastui-chart.css
  β  β  ββ toastui-chart.min.css
  β  ββ v4.0.0/
```

### μμ€ νμΌ λ€μ΄λ‘λ

- [κ° λ²μ μ μμ€μ½λ λ€μ΄λ‘λ νκΈ°](https://github.com/nhn/tui.chart/releases)

## μ¬μ©νκΈ°

### HTML

TOAST UI Chartκ° μμ±λ  μ»¨νμ΄λ μμλ₯Ό μΆκ°νλ€.

```html
<div id="chart"></div>
```

### μλ°μ€ν¬λ¦½νΈ

#### λΆλ¬μ€κΈ°

TOAST UI μ°¨νΈλ μμ±μ ν¨μλ₯Ό ν΅ν΄ μΈμ€ν΄μ€λ₯Ό μμ±ν  μ μλ€. μμ±μ ν¨μμ μ κ·ΌνκΈ° μν΄μλ νκ²½μ λ°λΌ μ κ·Όν  μ μλ μΈ κ°μ§ λ°©λ²μ΄ μ‘΄μ¬νλ€.

```js
/* namespace */
const chart = toastui.Chart;μ

/* Node.jsμ CommonJS */
const chart = require('@toast-ui/chart');

/* Node.jsμ ES6 */
import Chart from '@toast-ui/chart';
import { BarChart } from '@toast-ui/chart';
```

[Webpack 4 μμλ ν¨ν€μ§ λͺ¨λμ κ°μ Έμ¬ λ main νλλ³΄λ€ module νλμ μ μλ μ§μμ μ μ°μ μ μΌλ‘ κ°μ Έμ¨λ€](https://webpack.js.org/configuration/resolve/#resolvemainfields). λ§μ½ νλ‘μ νΈμμ Webpack 4λ₯Ό μ¬μ©νκ³  `require` κ΅¬λ¬Έμ μ¬μ©ν΄ `@toast-ui/chart`λ₯Ό λΆλ¬μ¨λ€λ©΄, module νλμ μ μλ ESM νμΌμ΄ λ‘λλ  κ²μ΄λ©°, require κ΅¬λ¬ΈμΌλ‘ κ°μ Έμ¬ μ μλλ‘ νΈλμ€ νμΌ λ  κ²μ΄λ€. νλ‘μ νΈμμ **UMD μ© λ²λ€ νμΌμ΄ νμ**νλ€λ©΄ `@toast-ui/chart/dist/toastui-chart.js` νΉμ `@toast-ui/chart/dist/toastui-chart.min.js` νμΌμ μ§μ  λ‘λνμ¬ μ¬μ©ν΄μΌ νλ€.

```js
const Chart = require('@toast-ui/chart/dist/toastui-chart.min.js'); // // UMD μ© λ²λ€ νμΌ λ‘λ
```

Webpack 5λ `exports` νλλ₯Ό μ§μνλ€. ν¨ν€μ§μμ μ μλ `exports` νλλ₯Ό λ³΄κ³  λͺ¨λ μ§μμ μ νλ¨ν  μ μλ€. λν μλμ κ°μ΄ μλΈ κ²½λ‘λ‘ μ κ·Όνμ¬ νμν μ°¨νΈ νμΌμ λ‘λν  μ μλ€.

```js
const Chart = require('@toast-ui/chart'); // ./dist/toastui-chart.js

import { BarChart } from '@toast-ui/chart'; // ./dist/esm/index.js

import BarChart from '@toast-ui/chart/bar';
import ColumnChart from '@toast-ui/chart/column';
import LineChart from '@toast-ui/chart/line';
import AreaChart from '@toast-ui/chart/area';
import LineAreaChart from '@toast-ui/chart/lineArea';
import ColumnLineChart from '@toast-ui/chart/columnLine';
import BulletChart from '@toast-ui/chart/bullet';
import BoxPlotChart from '@toast-ui/chart/boxPlot';
import TreemapChart from '@toast-ui/chart/treemap';
import HeatmapChart from '@toast-ui/chart/heatmap';
import ScatterChart from '@toast-ui/chart/scatter';
import LineScatterChart from '@toast-ui/chart/lineScatter';
import BubbleChart from '@toast-ui/chart/bubble';
import PieChart from '@toast-ui/chart/pie';
import NestedPieChart from '@toast-ui/chart/nestedPie';
import RadarChart from '@toast-ui/chart/radar';
```

### CSS

Chartλ₯Ό μ¬μ©νκΈ° μν΄μλ CSS νμΌμ μΆκ°ν΄μ€μΌ νλ€. import, requireλ₯Ό ν΅ν΄ CSS νμΌμ λΆλ¬μ€κ±°λ, CDNμ ν΅ν΄ λΆλ¬μ¬ μ μλ€.

* ES6 λͺ¨λ

```js
import '@toast-ui/chart/dist/toastui-chart.min.css'; // Chart μ€νμΌ
```

* Common JS

```js
require('@toast-ui/chart/dist/toastui-chart.min.css');
```

* CDN

```html
<link rel="stylesheet" href="https://uicdn.toast.com/chart/latest/toastui-chart.min.css" />
```


### μΈμ€ν΄μ€ λ§λ€κΈ°

μμ±μ ν¨μλ `el`, `data`, `options` μΈ κ°λ₯Ό μΈμλ‘ κ°λλ€. 

- el: μ°¨νΈλ₯Ό μμμμλ‘ κ°λ HTML μμ
- data: μ°¨νΈμ κΈ°λ°μ΄ λλ μ«μ λ°μ΄ν°
- options: λ²λ‘, μ λ ¬, ν΄ν ν¬λ§· λ± μ¬λ¬ κΈ°λ₯μ λνλ΄λ μ΅μ

```js
const el = document.getElementById('chart');
const data = {
  categories: ['Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
  series: [
    {
      name: 'Budget',
      data: [5000, 3000, 5000, 7000, 6000, 4000, 1000],
    },
    {
      name: 'Income',
      data: [8000, 4000, 7000, 2000, 6000, 3000, 5000],
    },
  ],
};
const options = {
  chart: { width: 700, height: 400 },
};

const chart = chart.barChart({ el, data, options });
// νΉ
const chart = new BarChart({ el, data, options });
```
![image](https://user-images.githubusercontent.com/35371660/105698632-79769d00-5f49-11eb-8ae5-0d0f648f9ac6.png)
