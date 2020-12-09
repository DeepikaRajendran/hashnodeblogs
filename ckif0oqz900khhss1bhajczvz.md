## How to draw Donut Chart using Google Charts in Angular ?

This article is about drawing a simple donut chart , using  [Google Charts](https://developers.google.com/chart/interactive/docs/gallery) 

There are many Angular wrapper npm packages available.
Here is one such wrapper for the Google Charts.

```
npm install angular-google-charts

``` 

After installation , proceed to import the Google Chart Module into the app.module.ts.

```
import { GoogleChartsModule } from "angular-google-charts";
imports: [
     GoogleChartsModule.forRoot()
]
```  

In app.component.html, add the below selector

```
 <google-chart #chart 
         [title]="title" 
         [type]="type" 
         [data]="data"
         [columnNames]="columnNames" 
         [options]="options" 
         [width]="width" 
         [height]="height">
 </google-chart>
``` 
and pass the values in app.component.ts

```
title = "Stocks";
type = 'PieChart';
width = 320;
height = 320;
columnNames = ['Name', 'Stocks'];
data: [string, number][] = [
    ['Apples', 5],
    ['Oranges', 3],
    ['Banana', 8]
];
options = {
    pieHole: 0.3 //this pieHole option makes the pieChart as Donut Chart
}
``` 
**Output:**

![Donut Chart.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1607371160012/ix3wDfEqi.png)

**Customize the colors**

```
options = {
    colors: ['green', 'pink', 'cyan'],
    pieHole: 0.3 //this pieHole option makes the pieChart as Donut Chart,
  }
``` 
![Donut Chart1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1607371868612/a1NatZFCX.png)

You can find more customizing options below:
**Customize the Legend** 

```
options = {
  legend: {
      position: 'bottom',
      alignment: 'start',
      maxLines: 5,
      textStyle: {
        color: 'grey',
        fontSize: 12
      }
    }
  }

``` 
**Customize the Title**

```
options = {
      titleTextStyle: {
      color: '#2964af',
      fontName: 'calibri',
      fontSize: '20'
    }
}
``` 
**Customize the chart**

```
options: {
 chartArea: {
      width: '100%',
      height: '100%',
      top: 50,
      left: 10,
      right: 10
    }
}
``` 

![Donut Chart2.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1607372568928/oSyCB8G4z.png)

**Customize pieSliceText**

```
options: {
    pieSliceText: 'label', // 'none', 'label', 'value', 'percentage'
}
``` 
For more options,  [Click here](https://developers.google.com/chart/interactive/docs/gallery/piechart?hl=en#configuration-options) 
