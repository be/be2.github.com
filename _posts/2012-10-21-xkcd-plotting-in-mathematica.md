---
layout: post
title: "xkcd plotting in mathematica"
description: "xkcd plotting in mathematica"
category: code
tags: [xkcd, plotting, mathematica, graphs]
---
{% include JB/setup %}

Mathematica's [stackexchange](http://mathematica.stackexchange.com) website is a resourceful place where users share their knowledge. From time to time a pearl is found. xkcd comics lovers, rejoice, it's possible to create xkcd graphs using Mathematica. User [amatya](http://mathematica.stackexchange.com/users/2039/amatya) wrote about an email he wanted to respond using xkcd graphs and how he came along with [Simon Woods](http://mathematica.stackexchange.com/users/862/simon-woods)' `xkcdconvert`. The one and only Simon answered the thread offering some cool examples of easy usage. Here's just a few:

##2D##

    xkcdConvert[BarChart[{1, 10}, ChartLegends -> {"Others", "XKCD"}, 
      PlotLabel -> "Popularity of questions on MMA.SE",
      ChartStyle -> {Red, Green}]]


![2d](http://f.cl.ly/items/2x3P1I0h2b083G1u192C/OBzhL.png)


##3D##

    xkcdConvert[BarChart3D[{3, 2, 1}, ChartStyle -> Red, FaceGrids -> None,
      Method -> {"Canvas" -> None}, ViewPoint -> {-2, -4, 1},
      PlotLabel -> "This is just silly"]]

![3d](http://f.cl.ly/items/1d3p1m0z420O2T1x2v3j/enter%20image%20description%20here.png)


##ListPlot##

    xkcdConvert[
     ListLinePlot[RandomInteger[10, 15], PlotMarkers -> Automatic]]

![listplot](http://f.cl.ly/items/3c102n1J1Z0A1n0d2p3T/enter%20image%20description%20here.png)

Read the full question entry @[http://mathematica.stackexchange.com](http://mathematica.stackexchange.com/questions/11350/xkcd-style-graphs)


