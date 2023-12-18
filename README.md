# LmsEqualizer
Least-Mean-Square Adaptive Equalization of a Noisy Dispersive Channel
This program is a web application written in Go which uses the html/template package to display the HTML.  To start the server, issue "go run equalization.go" in the Command Prompt.  To create an adaptive equalizer using LMS, enter http://127.0.0.1:8080/lmsequalizer in the web browser address bar.    Enter the LMS Equalization Options form data.  The adaptive filter coefficients are averaged over the specified number of trials to produce an ensemble average in order to reduce the variance.  The dispersive noisy channel is created using a pair of complex poles inside the unit circle with the specified signal-to-noise ratio (SNR).  The radius of the pole dictates how much dispersion of the square wave there is.  Numbers close to one produce the most corruption of the square wave input.  Numbers close to zero produce the least distortion.  The pole angle dictates which frequencies are emphasized in the output of the channel.  The output of the dispersive channel becomes the input to the adaptive filter.  The input to the dispersive channel is a pseudorandom square wave at the given frequency which alternates randomly between 1 and -1.  White Gaussian noise is added to the dispersive channel output with standard deviation given by the SNR.  After the adaptive filter is produced, the impulse or frequency response of the adaptive filter can be plotted.  The link <i>Plot Response</i> will take you to the page where you can choose the impulse (time domain) or frequency response.  For the frequency response, the FFT size, number of segments, and window can be chosen.  For this program, one segment with a rectangular window and an FFT size of 8192 is sufficient.  The link <i>Filter Signal</i> will take you to a page where you can display the various stage inputs and outputs. The Filter Signal Options have to be the same as the LMS Equalization Options you used to create the filter.  You have the choice to view the Channel Input, Channel Output, or Equalizer Output.  The Channel Input and Channel Output refer to the dispersive noisy channel.  Note that each form submittal will have a different input signal sequence. So the +/- 1 pseudorandom square wave will vary from one form submittal to the next. The performance measure for the adaptive filter is how closely the output is to +/- 1 as shown by the Channel Input.  In communication channels this type of distortion causes intersymbol interference.

<h4>Main Webpage</h4>

![LmsEqualizer_1](https://github.com/thomasteplick/LmsEqualizer/assets/117768679/cad85404-6575-4f51-9f72-916fb73a1014)

<h4>Plot Response Page</h4>

![plotResponse_ 95_10snr](https://github.com/thomasteplick/LmsEqualizer/assets/117768679/0b9c24bd-9453-4967-b68f-f2c2d7092662)

<h4>Impulse Response of the Adaptive Filter, Filter Order = 50</h4>

![time_response1](https://github.com/thomasteplick/LmsEqualizer/assets/117768679/72a52011-a53a-4ee5-b2a6-17909b85de8e)

<h4>Frequency Response of the Adaptive Filter</h4>

![freq_response2](https://github.com/thomasteplick/LmsEqualizer/assets/117768679/f38af026-2a59-4ff5-a447-83a79f910b24)

<h4>Filter Signal, Dispersive Channel Input, 10 Hz pseudorandom square wave, +/- 1</h4>

![filter_signal1](https://github.com/thomasteplick/LmsEqualizer/assets/117768679/e3342c4f-e389-4693-97bd-4b5cde27d28a)

<h4>Filter Signal, Dispersive Channel Output, SNR=10dB, Signal Frequency=10Hz, Poles at .95cos(10/180*PI*n) + j.95sin(10/180*PI*n)</h4>

![filter_signal2](https://github.com/thomasteplick/LmsEqualizer/assets/117768679/0a69f6ef-a4ce-486b-b44d-1808022b7321)

<h4>Filter Signal, Adaptive Equalizer Output</h4>

![filter_signal3](https://github.com/thomasteplick/LmsEqualizer/assets/117768679/613f3276-1670-4adf-b0b8-a4032a6e7bfb)

<h4>Filter Signal, Adaptive Equalizer Output</h4>

![filter_signal4](https://github.com/thomasteplick/LmsEqualizer/assets/117768679/dd0828ae-bcb4-42ca-845d-4e5eb9af65c0)
