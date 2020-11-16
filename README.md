<h1>Description</h1>
  This plugin aims to provide an easy and flexible artificial neural networks framework.

<h1>Elements</h1>
  -NeuralNet<br>
  -BaseNeuralNet<br>
  -NeuralNetMethods<br>
  -ForEachConnectionHandle
  
<h1>Documentacion</h1>

<h2>NeuralNet</h2>
  <h4>Inherits:</h4>
    BaseNeuralNet < Reference
  <h4>Description</h4>
    Ready to use net with sigmoidal activation function f(x)=x/sqrt(1+x^2).
                             
<h2>BaseNeuralNet</h2>
  <h4>Inherits:</h4>
    Reference
  <h4>Description</h4>
    Semi “abstract” class. Base for all neural networks.
  <h4>Properties</h4>
    Array net_structure - array of ints, describing each layer size, setget will return or pass duplicate<br>
    <br>Array data - array of arrays of float,s value of each connection (weight), setget will return or pass duplicate<br>
    <br>Array neuron_dat - array of arrays of ints, last activate neuron value or neuron error value depends whether was .calculate() or .back_propagation() method called last,   &nbsp &nbsp setget will return or pass duplicate<br>
    
<h2>NeuralNetMethods</h2>
  <h4>Inherits:</h4>
    Node
 <h4>Description</h4>
   Singleton container for methods that would cause cyclic dependency errors if placed as member functions. 
    
<h2>ForEachConnectionHandle</h2>
  <h4>Inherits:</h4>
    Reference
  <h4>Description</h4>
    “Abstract” class. Provides way to change connections (weights) in a custom way.

<h1>How to</h1>
