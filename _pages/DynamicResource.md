---
title: "DynamicResource"
permalink: /home/
layout: category
---

## 개요

DynamicResource에 대한 내용 검토

## 용도

등록된 Resource Key에 대한 동적인 변경이 필요한 경우 사용

## 내용

### 차이

#### [StaticResource]

미리 만들어둔 Style, Color등에 대한 범용적인 사용이 가능

#### [DynamicResource]

동적으로 리소스의 상태를 변경하고 싶을 때 사용


### 활용

#### [XAML]

"temp"라는 Key로 Resource 내 등록

```c#
<Grid>
    <Button x:Name="button"
            Background="{DynamicResource temp}"
            Content="버튼"
            Click="button_Click"/>
</Grid>
```

#### [C#]

등록된 키("temp")를 동적으로 변경

```C#
private void button_Click(object sender, RoutedEventArgs e)
{
    Random rnd = new Random();

    Color randomColor = Color.FromArgb(255, 
                                    (byte)rnd.Next(256), 
                                    (byte)rnd.Next(256), 
                                    (byte)rnd.Next(256));

    this.Resources["temp"] = new SolidColorBrush(randomColor);
}
```
