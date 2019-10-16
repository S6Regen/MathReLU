# MathReLU
Part 1.
ReLU is a literal switch. An electrical switch is n volts in, n volts out when on. Zero volts out when off.
A ReLU is x in, x out when on, zero when off.
The weighted sum (dot product) of a number of weighted sums is still a linear system.
For a particular input to a ReLU neural network all the switches are decidedly in either the on or off state. A particular linear projection is in effect between the input and output.
For a particular input and a particular output neuron there is a particular composition of weighted sums that may be condensed down into a single equivalent weighted sum.
You can look at that to see what it is looking at in the input or calculate some metrics like the angle between the input and the weight vector of the equivalent weighted sum.
If the angle is near 90 degrees and the output of the neuron is large then the vector length of weight vector must be large. That makes the output very sensitive to noise in the inputs. If the angle is near zero then there are averaging and central limit theorem effects that provide some error correction.
Since ReLU switches at zero there are no sudden discontinuities in the output of an ReLU neural network for gradual change in the input. It is a seamless system of switched linear projections.
There are efficient algorithms for calculating certain dot products like the FFT or WHT.
There is no reason you cannot incorporate those directly into ReLU neural networks since they are fully compatible.

https://github.com/S6Regen/Fixed-Filter-Bank-Neural-Networks

Part 2.

Maybe one or 2 people don't understand the weighted sum as a linear associative memory.

After storing 1 <pattern,response> item in the weighted sum the angle between the pattern and weight vector is zero and there is quite a strong amount of error correction from central limit theorem type averaging of the inputs.

After storing 2 <pattern,response> items in the weighted sum the angles between the input patterns and the weight vector are non-zero. And being non-zero the vector length of the weight vector must increase to get the wanted responses (dot product math.) That means any noise in the input patterns is magnified.

At some stage you have added so many items there is no error correction but exact responses are still possible.

Beyond that only responses contaminated by Gaussian noise are possible.

After storing n items one of the n input vectors must be the nearest in angular terms to the weight vector.  Any input closer in angular distance than than will produce a large spurious response.

The weighted sum is one of the few ways you can interpolate in the vastness of higher dimensional space and is relatively computationally efficient however the spurious responses are not funny. To some extent that may be dealt with by clipping the maximum and minimum outputs.  To prevent as it were super-normal responses to super-normal stimuli.

Part 3.
For a particular input and for a particular neuron in a ReLU neural network there is an equivalent single weighted sum.  And each of those weighed sums is looking at different things in the input.  Actually paying attention to different aspects of the input.
It also may be the case that the states of each ReLU switch in a neural network are information rich predicates for rapidly building decision trees for things related to what the neural network has learned like image classification.  Maybe you can quickly build a decision tree to see if a new sort of object is present without retraining the neural network from scratch. You can also examine the switch states from an entropy point of view, which obviously you would do anyway if you were building a tree using say the id3 algorithm.
