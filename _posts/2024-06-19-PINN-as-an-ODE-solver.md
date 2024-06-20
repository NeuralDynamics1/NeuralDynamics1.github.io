## First lesson; PINN as an ode solver!

# What are Physics-Informed Neural Networks?
Physics-Informed Neural Networks (PINNs) are a type of deep learning models that not only fit the data (as classical neural networks) but also incorporate physical laws into the training process (mostly through loss function). Unlike traditional neural networks (which only rely on data to learn patterns and make predictions), PINNs leverage the governing equations of the physical (dynamical) systems to improve accuracy and generalizability. Thus, PINNs not only fit the data but obey the physical constraints and symmetries.

# Multi-Layer Perceptron


A Multi-Layer Perceptron (MLP) is the most common type of deep learning alghorithim and essentially is a complex nonlinear function. The complexity and nonlinearity of an MLP increase with the number of neurons and layers it contains. The more layers and neurons an MLP has, the more complex it becomes, and consequently, it requires more data to train effectively. An MLP can be descibed as:

![image](https://github.com/NeuralDynamics1/NeuralDynamics1.github.io/assets/173298938/d4663bf0-6f52-488f-b204-a98632499344)



where n is the input dimention, and m is the output dimention.

Thus, an MLP is a powerful tool for learning complicated nonlinear data points and their dynamics.

In an MLP, each neuron in a layer is connected to every neuron in the preivious and next layer. We associate these conections as weights and biases( parameters) that the model learns during traininig.

We don't go deep into how to train them, and the only important part to consider is, the MLP is a highly complex nonlinear function that can fit the data.

# First Example; Simple Hormonic Oscillation

A simple harmonic oscillator describes a system where a mass 𝑚  is attached to a spring with spring constant 𝑘. The system oscillates back and forth around an equilibrium position due to the restoring force provided by the spring, which is proportional to the displacement 𝑥 from the equilibrium position and directed towards it.

The dynamics of the system are governed by Newton's second law of motion:

![image](https://github.com/NeuralDynamics1/NeuralDynamics1.github.io/assets/173298938/cdfa6474-dbf4-46dc-b557-3e47e2725501)




where:

𝐹 is the net force acting on the mass.

𝑚 is the mass of the object.

a is the acceleration of the mass which is the second derivatives of x.

--------------------------------------------------------------------------


For a spring, Hooke's law states that the restoring force 𝐹_spring is proportional to the displacement 𝑥 and is given by:

![image](https://github.com/NeuralDynamics1/NeuralDynamics1.github.io/assets/173298938/4b831916-e7a3-4c50-bdbc-f2b3391e7789)


where:

𝑘 is the spring constant.

𝑥 is the displacement from the equilibrium position.

The negative sign indicates that the force is directed opposite to the displacement.

----------------------------------------------------------------------------------

Substitute the expression for the restoring force from Hooke's law into Newton's second law:

![image](https://github.com/NeuralDynamics1/NeuralDynamics1.github.io/assets/173298938/80517d82-086c-4b89-8929-fbcc6e154ee3)


Rearrange the equation to obtain the standard form of the simple harmonic oscillator ODE:

![image](https://github.com/NeuralDynamics1/NeuralDynamics1.github.io/assets/173298938/1b8ee423-caa3-4be5-806c-ce5b75ce12db)


Introduce the angular frequency 𝜔, which is defined as:

![image](https://github.com/NeuralDynamics1/NeuralDynamics1.github.io/assets/173298938/29cdc532-cb16-4445-aa6d-edd9dc102c7f)


The derived ODE for the simple harmonic oscillator is:

![image](https://github.com/NeuralDynamics1/NeuralDynamics1.github.io/assets/173298938/5004ef62-fb65-4dfc-8c82-3af30fd350d2)

# Loss function



