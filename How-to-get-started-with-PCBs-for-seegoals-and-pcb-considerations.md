# How to get started

Start by creating a schematic, this is required to make a pcb. 

[This video](https://www.youtube.com/watch?v=3FGNw28xBr0) is a good concise full video from schematic to pcb.)

# I have started what do i need to think about?

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