# Stats Strided DSEMPN 📊

![Version](https://img.shields.io/badge/version-1.0.0-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)

Welcome to the **Stats Strided DSEMPN** repository! This project focuses on calculating the standard error of the mean for a double-precision floating-point strided array using a two-pass algorithm. If you want to dive right in, you can find the latest releases [here](https://github.com/Stevendelos/stats-strided-dsempn/releases).

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Algorithm Overview](#algorithm-overview)
- [Examples](#examples)
- [API Reference](#api-reference)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Introduction

In statistics, the standard error of the mean (SEM) provides insight into how much the sample mean is expected to vary from the true population mean. This project implements a two-pass algorithm that efficiently calculates the SEM for strided arrays. Strided arrays are useful when working with large datasets, as they allow for more efficient memory usage and access patterns.

## Installation

To get started, clone this repository and install the necessary dependencies:

```bash
git clone https://github.com/Stevendelos/stats-strided-dsempn.git
cd stats-strided-dsempn
npm install
```

You can also download the latest release from the [Releases section](https://github.com/Stevendelos/stats-strided-dsempn/releases). Make sure to execute the necessary files after downloading.

## Usage

To calculate the standard error of the mean, import the module and call the function with your strided array data:

```javascript
const sem = require('stats-strided-dsempn');

// Example strided array
const data = new Float64Array([1.0, 2.0, 3.0, 4.0, 5.0]);
const stride = 1; // Adjust as necessary

const result = sem(data, stride);
console.log(`Standard Error of the Mean: ${result}`);
```

## Algorithm Overview

The two-pass algorithm consists of the following steps:

1. **First Pass**: Calculate the mean of the data.
2. **Second Pass**: Calculate the standard deviation and then derive the standard error from the mean.

### Pass 1: Mean Calculation

The mean is calculated by summing all the elements and dividing by the number of elements. This gives us a baseline to work from.

### Pass 2: Standard Deviation and SEM Calculation

Once we have the mean, we compute the standard deviation. The SEM is then calculated using the formula:

\[ SEM = \frac{SD}{\sqrt{n}} \]

Where \( SD \) is the standard deviation and \( n \) is the number of elements.

## Examples

Here are a few examples to demonstrate the usage of the library:

### Example 1: Basic Calculation

```javascript
const sem = require('stats-strided-dsempn');

const data = new Float64Array([2.5, 3.5, 4.5, 5.5]);
const stride = 1;

const result = sem(data, stride);
console.log(`Standard Error of the Mean: ${result}`);
```

### Example 2: Strided Access

If you want to access elements with a stride, adjust the `stride` parameter accordingly:

```javascript
const data = new Float64Array([1.0, 2.0, 3.0, 4.0, 5.0, 6.0]);
const stride = 2; // Access every second element

const result = sem(data, stride);
console.log(`Standard Error of the Mean with stride: ${result}`);
```

## API Reference

### `sem(data, stride)`

- **Parameters**:
  - `data`: A `Float64Array` containing the input data.
  - `stride`: A number representing the step size to access elements in the array.
  
- **Returns**: The standard error of the mean as a number.

## Contributing

We welcome contributions! If you want to help improve this project, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Make your changes and commit them (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to the contributors who have helped improve this project.
- Special thanks to the developers of the libraries used in this project.

For further information and updates, feel free to check the [Releases section](https://github.com/Stevendelos/stats-strided-dsempn/releases).