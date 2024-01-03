Certainly! Here's the updated README with the provided Conditional Probability Tables (CPDs) included:

---

# Bayesian Network Implementation with pgmpy

This repository contains code for creating and visualizing a Bayesian Network using the `pgmpy` library in Python. Bayesian Networks are graphical models that represent probabilistic relationships among a set of variables. In this specific implementation, the Bayesian Network represents a series of events related to weather, traffic, accidents, and their impact on timing and relationships with friends.

## Dependencies

Make sure you have the following dependencies installed before running the code:

- `pgmpy`
- `pandas`
- `networkx`
- `matplotlib`

You can install these dependencies using the following command:

```bash
pip install pgmpy pandas networkx matplotlib
```

## Usage

1. **Clone the Repository:**

    ```bash
    git clone https://github.com/your-username/bayesian-network-pgmpy.git
    ```

2. **Navigate to the Project Directory:**

    ```bash
    cd bayesian-network-pgmpy
    ```

3. **Run the Code:**

    Execute the `bayesian_network.py` script to create the Bayesian Network, estimate Conditional Probability Tables (CPDs) using Maximum Likelihood Estimation, and visualize the network.

    ```bash
    python bayesian_network.py
    ```

4. **View the Bayesian Network:**

    The script generates a visualization of the Bayesian Network using `networkx` and `matplotlib`. The graphical representation provides insights into the probabilistic dependencies among different events.

## Customization

Feel free to customize the Bayesian Network structure by modifying the directed edges in the code. Additionally, you can adapt the visualization settings in the `nx.draw()` function to suit your preferences.

## Conditional Probability Tables (CPDs)

Below are the Conditional Probability Tables (CPDs) estimated using Maximum Likelihood Estimation:

### CPD for Rainy given ['Rainy']:
```
+--------------+-----+
| Rainy(False) | 0.5 |
+--------------+-----+
| Rainy(True)  | 0.5 |
+--------------+-----+
```

### CPD for Raincoat given ['Raincoat', 'Rainy']:
```
+-----------------+--------------+-------------+
| Rainy           | Rainy(False) | Rainy(True) |
+-----------------+--------------+-------------+
| Raincoat(False) | 0.5          | 0.5         |
+-----------------+--------------+-------------+
| Raincoat(True)  | 0.5          | 0.5         |
+-----------------+--------------+-------------+
```

### CPD for Rush_Hour given ['Rush_Hour']:
```
+------------------+-----+
| Rush_Hour(False) | 0.5 |
+------------------+-----+
| Rush_Hour(True)  | 0.5 |
+------------------+-----+
```

### CPD for Traffic given ['Traffic', 'Rush_Hour']:
```
+----------------+------------------+-----------------+
| Rush_Hour      | Rush_Hour(False) | Rush_Hour(True) |
+----------------+------------------+-----------------+
| Traffic(False) | 1.0              | 0.0             |
+----------------+------------------+-----------------+
| Traffic(True)  | 0.0              | 1.0             |
+----------------+------------------+-----------------+
```

### CPD for Accident given ['Accident', 'Rush_Hour']:
```
+-----------------+------------------+-----------------+
| Rush_Hour       | Rush_Hour(False) | Rush_Hour(True) |
+-----------------+------------------+-----------------+
| Accident(False) | 1.0              | 0.0             |
+-----------------+------------------+-----------------+
| Accident(True)  | 0.0              | 1.0             |
+-----------------+------------------+-----------------+
```

### CPD for Shortcuts given ['Shortcuts', 'Traffic']:
```
+------------------+----------------+---------------+
| Traffic          | Traffic(False) | Traffic(True) |
+------------------+----------------+---------------+
| Shortcuts(False) | 1.0            | 0.0           |
+------------------+----------------+---------------+
| Shortcuts(True)  | 0.0            | 1.0           |
+------------------+----------------+---------------+
```

### CPD for Timing given ['Timing', 'Late_Before', 'Shortcuts']:
```
+-----------------+--------------------+-----+-------------------+-------------------+
| Late_Before     | Late_Before(False) | ... | Late_Before(True) | Late_Before(True) |
+-----------------+--------------------+-----+-------------------+-------------------+
| Shortcuts       | Shortcuts(False)   | ... | Shortcuts(False)  | Shortcuts(True)   |
+-----------------+--------------------+-----+-------------------+-------------------+
| Timing(Late)    | 0.0                | ... | 0.5               | 1.0               |
+-----------------+--------------------+-----+-------------------+-------------------+
| Timing(On_time) | 1.0                | ... | 0.5               | 0.0               |
+-----------------+--------------------+-----+-------------------+-------------------+
```

### CPD for Late_Before given ['Late_Before']:
```
+--------------------+-----+
| Late_Before(False) | 0.5 |
+--------------------+-----+
| Late_Before(True)  | 0.5 |
+--------------------+-----+
```

### CPD for Friend_Angry given ['Friend_Angry', 'Timing']:
```
+---------------------+--------------+-----------------+
| Timing              | Timing(Late) | Timing(On_time) |
+---------------------+--------------+-----------------+
| Friend_Angry(False) | 0.0          | 1.0             |
+---------------------+--------------+-----------------+
| Friend_Angry(True)  | 1.0          | 0.0             |
+---------------------+--------------+-----------------+
```

## Data

The script uses a sample dataset represented as a Pandas DataFrame. It's important to replace this sample data with your actual dataset for meaningful analysis.

## Acknowledgments

- [pgmpy Documentation](https://pgmpy.org/)
- [networkx Documentation](https://networkx.github.io/)
- [matplotlib Documentation](https://matplotlib.org/)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to further modify the README as needed.
