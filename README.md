<h1>Description</h1>
  This plugin aims to provide an easy and flexible artificial neural networks framework.

<h1>Elements</h1>
  -NeuralNet<br>
  -BaseNeuralNet<br>
  -NeuralNetMethods<br>
  -ForEachConnectionHandle
  
<h1>Documentacion</h1>
Do not call functions with “_” prefix directly.

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
    Array net_structure - Array of ints describing each layer size. setget will return or pass duplicate<br>
    <br>Array data - Array of arrays of floats, value of each connection (weight). setget will return or pass duplicate<br>
    <br>Array neuron_dat - Array of arrays of floats, last neuron value or neuron error value, depends on whether was .calculate() or .back_propagation() method called last, setget will return or pass duplicate<br>
  <h4>Methods</h4>
     BaseNeuralNet new(Array net_structure) - Creates a new object sets self.net_structure to duplicate of net_structure. Sets value of each connection to 0.<br>
     <br>void add_random(float min_val, float max_val) - Adds random value to each connection.<br>
     <br>void multiply_random(float min_val, float max_val) - Multiplies each connection by random value.<br>
     <br>Array calculate(Array input) - Runs net. Returns Array of floats of size of last self.net_structure cell value.<br>
     <br>void back_propagation(Array error, float lerning_factor) - Propagates error and correct connections.<br>
     <br>float _actiavte(float e) - “Virtual” function. Default return value is always zero. Override it with activation function of your choice. <br>
     <br>float _derivative(float x) - “Virtual” function. Derivative of activation function in point x. No need to overwrite it if you don't plan to use back propagation.<br>
     <br>void for_each_connection(ForEachConnectionHandle handle) - Calls handle._for_each_connection() for each connection where x and y (x is closer to or is in the output layer) are neurons that it is connecting. Z is the first self.data index and index is second.In another words connection is data[z][index]. Index is calculated from this formula i = x*(net_structure[z]+1)+y. Net is self.<br>
    
<h2>NeuralNetMethods</h2>
  <h4>Inherits:</h4>
    Node
 <h4>Description</h4>
   Singleton container for methods that would cause cyclic dependency errors if placed as member functions. 
 <h4>Methods</h4>
   String print_net(BaseNeuralNet net) - converts net to JSON string.<br>
   <br>BaseNeuralNet parse_net(String json) - converts String back to BaseNeuralNet.<br>
    
<h2>ForEachConnectionHandle</h2>
  <h4>Inherits:</h4>
    Reference
  <h4>Description</h4>
    “Abstract” class. Provides way to change connections (weights) in a custom way.
  <h4>Methods</h4>
    void _for_each_connection(int x, int y, int z, int index, BaseNeuralNet net)

<h1>How to</h1>
