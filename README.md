# NMEA-and-Node-Red

jbcodemonkey update:  
-Added \n input parser to process inputs line by line.  
-Added output sensor blocks for HomeAssistant.  
-Added support for AWS and AWA via $???VWR.  
-Tested w SignalK and other tcp server nmea simulators.  
-Changed nmea filter node to process only the last three characters of sentence intros so instead of parsing \$GPAAM, we're processing all $??AAM sentences and passing them along. This allows handling of data from alternate vendors without code changes, though I suspect at some point it will be necessary to select which feeds are desired for a given sentence class when multiple devices provide the same class of data.

Original Content:
Disclaimer: Since these are my first steps using node red and Javascript not every step or piece of code is the best solution that one can imagine. It's like a PoC. Use what you want to use and ignore the rest.

The NMEA183 data collected is delivered by an ip-based NMEA device, e.g. a chart plotter, openplotter etc.
The following sentences are processed:  $GPAAM, $GPAPB, $GPBOD, $GPGGA, $GPGLC, $GPGLL, $GPGSA, $GPGSV, $GPRMB, 
$GPRMC, $GPVTG, $GPXTE, $GPZDA, $IIXDR, $SDDBT, $SDDPT, $SDHDG, $SDMTW, $SDVHW, $SDVLW, $WIMWD, $WIMWV

Usage: copy the code and insert in in node red using: import -> cliboard -> clipboard
  
