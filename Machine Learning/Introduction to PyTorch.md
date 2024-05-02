## PyTorch Tensors

### Import PyTorch:

```python
import torch
```

### PyTorch Tensors: 

**Basic Tensor Manupulations:**

```python
z = torch.zeros(5, 3)
print(z)
print(z.dtype)
```

Output:
```Terminal
tensor([[0., 0., 0.],
        [0., 0., 0.],
        [0., 0., 0.],
        [0., 0., 0.],
        [0., 0., 0.]])
torch.float32
```

```python
i = torch.ones((5, 3), dtype=torch.int16)
print(i)
```

Output:
```terminal
tensor([[1, 1, 1],
        [1, 1, 1],
        [1, 1, 1],
        [1, 1, 1],
        [1, 1, 1]], dtype=torch.int16)
```

```python
torch.manual_seed(1729)
r1 = torch.rand(2, 2)
print('A random tensor:')
print(r1)

r2 = torch.rand(2, 2)
print('\nA different random tensor:')
print(r2) # new values

torch.manual_seed(1729)
r3 = torch.rand(2, 2)
print('\nShould match r1:')
print(r3) # repeats values of r1 because of re-seed
```

Output:
```terminal
A random tensor:
tensor([[0.3126, 0.3791],
        [0.3087, 0.0736]])

A different random tensor:
tensor([[0.4216, 0.0691],
        [0.2332, 0.4047]])

Should match r1:
tensor([[0.3126, 0.3791],
        [0.3087, 0.0736]])
```

**Artihmetic Operations:**

```python
ones = torch.ones(2, 3)
print(ones)

twos = torch.ones(2, 3) * 2 # every element is multiplied by 2
print(twos)

threes = ones + twos       # addition allowed because shapes are similar
print(threes)              # tensors are added element-wise
print(threes.shape)        # this has the same dimensions as input tensors

r1 = torch.rand(2, 3)
r2 = torch.rand(3, 2)
# uncomment this line to get a runtime error
# r3 = r1 + r2
```

Output:
```terminal
tensor([[1., 1., 1.],
        [1., 1., 1.]])
tensor([[2., 2., 2.],
        [2., 2., 2.]])
tensor([[3., 3., 3.],
        [3., 3., 3.]])
torch.Size([2, 3])
```

**Mathematical Operations:**

```python
r = (torch.rand(2, 2) - 0.5) * 2 # values between -1 and 1
print('A random matrix, r:')
print(r)

# Common mathematical operations are supported:
print('\nAbsolute value of r:')
print(torch.abs(r))

# ...as are trigonometric functions:
print('\nInverse sine of r:')
print(torch.asin(r))

# ...and linear algebra operations like determinant and singular value decomposition
print('\nDeterminant of r:')
print(torch.det(r))
print('\nSingular value decomposition of r:')
print(torch.svd(r))

# ...and statistical and aggregate operations:
print('\nAverage and standard deviation of r:')
print(torch.std_mean(r))
print('\nMaximum value of r:')
print(torch.max(r))
```

Output:
```terminal
A random matrix, r:
tensor([[ 0.9956, -0.2232],
        [ 0.3858, -0.6593]])

Absolute value of r:
tensor([[0.9956, 0.2232],
        [0.3858, 0.6593]])

Inverse sine of r:
tensor([[ 1.4775, -0.2251],
        [ 0.3961, -0.7199]])

Determinant of r:
tensor(-0.5703)

Singular value decomposition of r:
torch.return_types.svd(
U=tensor([[-0.8353, -0.5497],
        [-0.5497,  0.8353]]),
S=tensor([1.1793, 0.4836]),
V=tensor([[-0.8851, -0.4654],
        [ 0.4654, -0.8851]]))

Average and standard deviation of r:
(tensor(0.7217), tensor(0.1247))

Maximum value of r:
tensor(0.9956)
```

## PyTorch Models

## Training PyTorch Model

### Training Loop

```python
for epoch in range(2):  # loop over the dataset multiple times

    running_loss = 0.0
    for i, data in enumerate(trainloader, 0):
        # get the inputs
        inputs, labels = data

        # zero the parameter gradients
        optimizer.zero_grad()

        # forward + backward + optimize
        outputs = net(inputs)
        loss = criterion(outputs, labels)
        loss.backward()
        optimizer.step()

        # print statistics
        running_loss += loss.item()
        if i % 2000 == 1999:    # print every 2000 mini-batches
            print('[%d, %5d] loss: %.3f' %
                  (epoch + 1, i + 1, running_loss / 2000))
            running_loss = 0.0

print('Finished Training')
```

The training code iterates over the dataset for a fixed number of passes called **epochs**. Each epoch represents a complete pass through the entire dataset. Here’s a step-by-step breakdown:

```python
for epoch in range(2):  # Two epochs
```

- **Epochs**: Each `epoch` is one full cycle through the training dataset, allowing the model to learn from the entire data multiple times.

### Batch Processing

```python
for i, data in enumerate(trainloader, 0):
```

- **Data Loader**: `trainloader` batches the data and serves it in a manageable size (batch size of 4 in this case). Each iteration of the loop fetches one batch of data.
- **`i`**: This is the batch index.
- **`data`**: A tuple containing a batch of inputs and their corresponding labels.

### Understanding Batches and Batch Size

- **Batch Size**: The number of data samples processed together in one step. In this scenario, the batch size is 4, meaning each batch contains 4 images and their corresponding labels.
- **Number of Batches**: Calculated by dividing the total number of samples by the batch size. For a dataset like CIFAR-10 with 50,000 training images, the number of batches per epoch is:
	$$\text{Number of Batches} = \frac{\text{Total Number of Samples}}{\text{Batch Size}}$$

	For a dataset like CIFAR-10 with 50,000 training images and a batch size of 4, the calculation is:
	$$\text{Number of Batches} = \frac{50,000}{4} = 12,500$$

### Data Handling and Model Handling

```python
inputs, labels = data  # Load data
```

- **Tuple Unpacking**: This operation extracts inputs and labels from the `data` tuple, assigning them to the `inputs` and `labels` variables, respectively. This is crucial for clarity and reducing errors in data handling.

### Forward and Backward Passes

```python
optimizer.zero_grad()  # Reset gradients
outputs = net(inputs)  # Forward pass
loss = criterion(outputs, labels)  # Compute loss
loss.backward()  # Backward pass, compute gradients
optimizer.step()  # Update model parameters
```

- **Zero Gradient Buffers**: It's crucial to reset gradients to zero before starting backpropagation because gradients accumulate by default in PyTorch.
- **Forward Pass**: The model computes predictions (`outputs`) based on the input data.
- **Loss Calculation**: The discrepancy between the predictions and the true data (`labels`) is calculated using a **loss function** (`criterion`), typically `nn.CrossEntropyLoss()` for classification tasks.
- **Backward Pass**: Gradients of the loss function with respect to the model parameters are computed.
- **Optimize**: Parameters are updated using an **optimizer** (`SGD` with learning rate and momentum in this case), which adjusts them based on the gradients to minimize the loss.

### Logging and Monitoring

```python
running_loss += loss.item()  # Accumulate loss
if i % 2000 == 1999:  # Every 2000 mini-batches
    print(f'[{epoch + 1}, {i + 1}] loss: {running_loss / 2000:.3f}')
    running_loss = 0.0  # Reset accumulated loss
```

- **Running Loss**: Tracks the loss over several batches to provide an average loss, which helps in monitoring the training progress.
- **Periodic Logging**: Every 2000 batches, the average loss is printed to give insights into how well the model is learning.






