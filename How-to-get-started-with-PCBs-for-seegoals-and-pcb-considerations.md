# How to get started

First and foremost, expect that things will not work or that there will be issues in the first design. Keep that in mind, try not to make too large of a design and divide PCBs into smaller boards that can be tested to make sure a specific part works. 

Start by creating a schematic, this is required to make a pcb. 

[This video](https://www.youtube.com/watch?v=3FGNw28xBr0) is a good concise full video from schematic to pcb.)

## How do i know which components or ICs to use?

This is hard to say, and requires a lot of googling. Looking what other teams have done through the TDP search engine is likely the best starting point. After that you can try to find the most simple ICs, which works for your requirement. A lot of googling is likely required here.

## Capacitors and inductances

From our experience these components are just used to make signals more smooth which is important, but also don't think to hard about it. A capacitor discharges voltage when there is a voltage drop, an inductor "keeps" some current which is released when the current drops.

Follow the guidelines from the datasheets of components you use and this will likely be fine.

## Tools

Majority of the project designs are created using KiCad, 

## Trace widths
A mistake we made early on was using to small track widths, likely causing one of the traces to burn off. 
This is very important for high current traces. You can use online tools or KiCads "Calculator Tools" to calculate and make sure that the width or large enough.

## Vias

Same as trace widths, vias also have a maximum current. Use calulator tools and place several vias for high current 

## Trace Distance

There is always cross talk between traces, this is caused by high transients when a signal goes high or low. For high speed signals this is an important consideration. As a general rule of thumb make sure that you place traces as far away as possible from other traces, this also applies for traces between multi-layer boards.

# More learning

* [A very long (but good), and comprehensive video about the whole process of designen for STM32 platforms](https://youtu.be/14_jh3nLSsU)
* [Mistakes to think about](https://www.youtube.com/watch?v=hkSad4n76Lc)
* [Noise between traces](https://www.youtube.com/watch?v=67mRFXSbCw0) 
* [How to think about communication protocols when designing pcbs](https://www.youtube.com/watch?v=eheh938ESU0)
* [Video about mistakes, and showing how to think about via and trace width](https://www.youtube.com/watch?v=D0X76Kbf8fQ)