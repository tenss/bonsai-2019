---
layout: slides
title: 1. Introduction to data acquisition
permalink: /slides/data/
---

<section data-markdown data-separator="^\n---\n$" data-separator-vertical="^\n--\n$">
<script type="text/template">

![TENSS](http://tenss.ro/images/header2016.png)

[tenss.ro/materials](http://neurogears.org/tenss-2019/)

### Introduction to data acquisition
How to measure almost anything with a computer

---

<!-- .element: data-transition="none" -->
#### How do you get data into a computer?

<table>
  <tr>
    <td class="fragment" width="30%"><small>What is the temperature outside?</small></td>
    <td width="30%"></td>
    <td class="fragment" width="30%"><small>How do you get that <b>value</b> into a computer?</small></td>
  </tr>
</table>

<div>
  <img class="fragment" src="../../assets/images/measuring-0.svg"/>
  <img class="fragment" src="../../assets/images/measuring-1.svg" style="position: absolute; left: 99px;" />
</div>

--

<!-- .element: data-transition="none" -->
#### How do you get data into a computer?

![Daq](../../assets/images/daq.svg)

--

<!-- .element: data-transition="none" -->
#### Computers can only measure voltage

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-sensor.svg" /></td>
    <td class="fragment" style="vertical-align: middle;"><img src="../../assets/images/daq-thermistor.svg" /></td>
  </tr>
</table>

--

<!-- .element: data-transition="none" -->
#### Computers can only measure voltage

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-sensor.svg" /></td>
    <td class="fragment" style="vertical-align: middle;"><img src="../../assets/images/daq-ohm.svg" /></td>
  </tr>
</table>

--

<!-- .element: data-transition="default none" -->
#### Bio-electricity and Ohm's Law

<table>
  <tr>
    <td style="vertical-align: middle;"><a href="https://en.wikipedia.org/wiki/Alessandro_Volta#/media/File:Alessandro_Volta.jpeg"><img src="https://upload.wikimedia.org/wikipedia/commons/5/52/Alessandro_Volta.jpeg" /></a></td>
    <td style="vertical-align: middle;"><a href="https://en.wikipedia.org/wiki/Georg_Ohm#/media/File:Georg_Simon_Ohm3.jpg"><img src="https://upload.wikimedia.org/wikipedia/commons/2/2a/Georg_Simon_Ohm3.jpg" /></a></td>
    <td style="vertical-align: middle;"><a href="https://en.wikipedia.org/wiki/Andr%C3%A9-Marie_Amp%C3%A8re#/media/File:Ampere_Andre_1825.jpg"><img src="https://upload.wikimedia.org/wikipedia/commons/c/c0/Ampere_Andre_1825.jpg" /></a></td>
  </tr>
  <tr>
    <td><small>Alessandro Volta</small></td>
    <td><small>Georg Ohm</small></td>
    <td><small>André-Marie Ampère</small></td>
  </tr>
</table>

--

<!-- .element: data-transition="none" -->
#### Computers can only measure voltage

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-sensor.svg" /></td>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-ohm.svg" /></td>
  </tr>
</table>

--

<!-- .element: data-transition="none" -->
#### Voltage divider: a readout of variable resistance

![Voltage](../../assets/images/daq-voltage.svg)

--

<!-- .element: data-transition="none" -->
![Voltage](../../assets/images/heavy-load.svg)

--

<!-- .element: data-transition="none" -->
![Voltage](../../assets/images/heavy-load-labels.svg)

--

<!-- .element: data-transition="none" -->
#### Remaining "black-boxes"

1. Diode
2. Transistor (MOSFET)
3. Analog to Digital Converter (ADC)

--

<!-- .element: data-transition="none" -->
#### Analog to Digital Converter (ADC)

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-adc.svg" /></td>
    <td class="fragment" style="vertical-align: middle;"><img src="../../assets/images/daq-transistor.svg" /></td>
  </tr>
</table>

--

<!-- .element: data-transition="none" -->
#### The simplest ADC: 1-bit comparator

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-adc1.svg" /></td>
    <td style="vertical-align: middle;"><a href="https://en.wikipedia.org/wiki/Comparator#/media/File:Opamp105.gif"><img src="https://upload.wikimedia.org/wikipedia/commons/f/f5/Opamp105.gif" /></a></td>
  </tr>
</table>

--

<!-- .element: data-transition="none" -->
#### Counting in Binary

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-adc.svg" /></td>
    <td style="vertical-align: middle;"><img width="320" src="../../assets/images/binary-1.svg" /></td>
  </tr>
</table>

--

<!-- .element: data-transition="none" -->
#### Counting in Binary

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-adc.svg" /></td>
    <td style="vertical-align: middle;"><img width="320" src="../../assets/images/binary-2.svg" /></td>
  </tr>
</table>

--

<!-- .element: data-transition="none" -->
#### Counting in Binary

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-adc.svg" /></td>
    <td style="vertical-align: middle;"><img width="320" src="../../assets/images/binary-3.svg" /></td>
  </tr>
</table>

--

<!-- .element: data-transition="none" -->
#### Flash ADC

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-adc.svg" /></td>
    <td style="vertical-align: middle;"><a href="https://en.wikipedia.org/wiki/Flash_ADC#/media/File:Flash_ADC.png"><img src="https://upload.wikimedia.org/wikipedia/commons/3/3a/Flash_ADC.png" /></a></td>
  </tr>
</table>

--

<!-- .element: data-transition="none" -->
#### Flash ADC

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-adc-specs.svg" /></td>
    <td style="vertical-align: middle;"><a href="https://en.wikipedia.org/wiki/Flash_ADC#/media/File:Flash_ADC.png"><img src="https://upload.wikimedia.org/wikipedia/commons/3/3a/Flash_ADC.png" /></a></td>
  </tr>
</table>

--

<!-- .element: data-transition="none default" -->
#### Successive Approximation ADC
<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-adc.svg" /></td>
    <td style="vertical-align: middle;"><a href="https://en.wikipedia.org/wiki/Successive_approximation_ADC#/media/File:SA_ADC_block_diagram.png"><img width="300" height="240" src="https://upload.wikimedia.org/wikipedia/commons/6/61/SA_ADC_block_diagram.png" /></a></td>
  </tr>
</table>

--

<!-- .element: data-transition="none default" -->
#### Successive Approximation ADC
<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/daq-adc-rate.svg" /></td>
    <td style="vertical-align: middle;"><a href="https://en.wikipedia.org/wiki/Successive_approximation_ADC#/media/File:SA_ADC_block_diagram.png"><img width="300" height="240" src="https://upload.wikimedia.org/wikipedia/commons/6/61/SA_ADC_block_diagram.png" /></a></td>
  </tr>
</table>

---

<!-- .element: data-transition="none" -->
#### How do you get data out of a computer?

![Control](../../assets/images/control.svg)

--

<!-- .element: data-transition="none" -->
#### TTL: Transistor-Transistor Logic

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/control-ttl.svg" /></td>
    <td class="fragment" style="vertical-align: middle;"><img src="../../assets/images/daq-ohm.svg" /></td>
  </tr>
</table>

--

<!-- .element: data-transition="none" -->
#### Brushless DC Motor: DC to AC converter

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/control-motor.svg" /></td>
    <td class="fragment" style="vertical-align: middle;"><a href="https://en.wikipedia.org/wiki/Brushless_DC_electric_motor#/media/File:Poles.jpg"><img width="300" height="240" src="https://upload.wikimedia.org/wikipedia/commons/6/6e/Poles.jpg" /></a></td>
  </tr>
</table>

--

<!-- .element: data-transition="none" -->
#### Pulse-Width Modulation (PWM)

<table>
  <tr>
    <td style="vertical-align: middle;"><img src="../../assets/images/control-pwm.svg" /></td>
    <td class="fragment" style="vertical-align: middle;">
      <div>
        <a href="https://en.wikipedia.org/wiki/Pulse-width_modulation#/media/File:PWM,_3-level.svg"><img width="320" height="221" src="https://upload.wikimedia.org/wikipedia/commons/8/8e/PWM%2C_3-level.svg" /></a>
        <div>
          <small>
          <span style="color:blue; font-size:100%; line-height:1;" title="Blue">■</span> Pulse-width modulated binary logic<br>
          <span style="color:red; font-size:100%; line-height:1;" title="Red">■</span> Induced sine-like current
          </small>
        </div>
      </div>
    </td>
  </tr>
</table>


</script>
</section>
