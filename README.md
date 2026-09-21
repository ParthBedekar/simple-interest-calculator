# Simple Interest Calculator

A Bash script that calculates simple interest based on user-provided principal amount, annual interest rate, and time period. This is a beginner-friendly command-line tool built as part of a GitHub and Git version control learning exercise.

## What is Simple Interest?

Simple interest is calculated using the formula:


Where:
- **Principal (P)** — the initial amount of money
- **Rate (R)** — the annual interest rate (as a percentage)
- **Time (T)** — the time period, in years

## Features

- Interactive command-line prompts for input
- Calculates simple interest and total payable amount
- Displays results with two decimal precision
- Lightweight — no dependencies beyond standard Bash and `bc`

## Requirements

- A Unix-like environment (Linux, macOS, WSL) with Bash installed
- `bc` (basic calculator) installed on your system

To install `bc` on Debian/Ubuntu-based systems:
```bash
sudo apt-get install bc
```

## Usage

1. Clone this repository:
```bash
   git clone https://github.com/ParthBedekar/github-final-project.git
   cd github-final-project
```

2. Make the script executable:
```bash
   chmod +x simple-interest.sh
```

3. Run the script:
```bash
   ./simple-interest.sh
```

## Script Overview

The script (`simple-interest.sh`) works as follows:

```bash
#!/bin/bash

echo "--- Simple Interest Calculator ---"

read -p "Enter Principal Amount: " principal
read -p "Enter Annual Rate of Interest (in %): " rate
read -p "Enter Time Period (in years): " time

interest=$(echo "scale=2; ($principal * $rate * $time) / 100" | bc)
total=$(echo "scale=2; $principal + $interest" | bc)

echo "----------------------------------"
echo "Principal: $principal"
echo "Interest Rate: $rate%"
echo "Time: $time years"
echo "Calculated Simple Interest: $interest"
echo "Total Amount Payable: $total"
```

It takes three inputs — principal, rate, and time — and uses `bc` for precise decimal calculations, since Bash alone can't handle floating-point math.

## License

This project is licensed under the Apache License 2.0 — see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Code of Conduct

This project adheres to a [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you agree to uphold this code.
