## Introducing Tensorflow

* Open source software for numerical computation
* Uses data flow graphs
* Nodes in the graph represents mathematical operators
* Edges represents tensors, tensors are multidimensional arrays, essentially data fed into those operators.

## Tensor object

* An output produced by an operation.
* A symbolic handle to the output of an operation. Does not hold any value
* Defined using Python class tf.Tensor
  * A tensor object, tf.Tensor can be of any type defined by class [tf.Tensor] [2]
  * It includes, tf.float32, tf.float64, tf.int8....., for a complete list of DTypes look at [tf.Tensor][2]
* A tensor object can be either a constant, variable or a placeholder. In this section we will see an example for constant.

## Constant

* Constants true to their name never changes once initialized.
* A constant is typically created using tf.constant class.
* Some python objects can be converted to tensors using [tf.convert_to_tensor][3] function.

		# Create a tensor constant
		a_constant = tf.constant(20, shape = [1], dtype = tf.float32, name = "a_constant")
		# Convert a numpy array to a tensor object
		conv_array =  tf.convert_to_tensor(np.arange(1,10,0.2), dtype = tf.float32, name = "conv_array")



The above code segment gives two ways of creating a constant. Tensor constant a_constant in the above example is created using tf.constant class, as float32. The parameter name is optional, but it will be useful if we need to inspect the constant in later stage during debugging. The tensor constant conv_array is created using function tf.convert_to_tensor, a numpy array is converted to a constant in this case.

Finally to complete the example let us add these two constants.
	
	# Define a simple addition operation
	op_add = tf.add(a_constant, conv_array, name = "op_add")


## Session

* Session is very important concept in tensorflow. This is where the actual computation takes place.
* It defines the environment in which all operations are executed. 
    
		# Create a graph session
		session = tf.Session()
		output  = session.run(op_add)

A session is created using tf.Session class. The run function is used to execute the operations.
Once completed the session needs to be closed, to release all the resources held by the session.

		# Close the session
		session.close()

The code segment correponding to creating the constants and declaring the addion operation is 'graph building'. When the operation involving the operators is called by run function of session object, the graph is evaluated.


## Variables

* Memory buffers to hold tensor objects


## Segmentation

* Segmentation is partitioning of a tensor along with first dimension, i.e. mapping of rows to segments.
* 


## Reference
[1] https://www.tensorflow.org/versions/r0.7/how_tos/variables/index.html
[2] https://www.tensorflow.org/versions/r0.7/api_docs/python/framework.html#DType
[3] https://www.tensorflow.org/versions/r0.7/api_docs/python/framework.html#convert_to_tensor



[1]: https://www.tensorflow.org/versions/r0.7/how_tos/variables/index.html
[2]: https://www.tensorflow.org/versions/r0.7/api_docs/python/framework.html#DType
[3]: https://www.tensorflow.org/versions/r0.7/api_docs/python/framework.html#convert_to_tensor


