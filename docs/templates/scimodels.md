# Intro

`SciModel` is similar to Keras' `Model`, prepared to make scientific model creation effortless. 
The inputs are of `Variable` objects, and the outputs are `Target` objects.
As an example:  

```python
from sciann import Variable, Functional, SciModel, Data

x = Variable('x')
y = Variable('y')

Fxy = Functional('Fxy', [x, y], 
                 hidden_layers=[10, 20, 10],
                 activation='tanh')

model = SciModel([x,y], Data(Fxy))
```

`SciModel` can be trained by calling `model.train`. 

```python
training_history = model.train([X_data, Y_data], Fxy_data)
```

`training_history` object records the loss for each epoch as well as other parameters. 
Check Keras' documentation for more details.   

`SciModel` object also provides functionality such as `predict` and `save`.  

---

{{autogenerated}}
