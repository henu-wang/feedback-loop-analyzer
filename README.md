# Feedback Loop Analyzer

Analyze and optimize feedback loops in systems -- from business processes to personal habits to market dynamics. Understand what drives reinforcing and balancing behaviors.

## Overview

Feedback Loop Analyzer is a Python toolkit for identifying, classifying, and optimizing feedback loops in complex systems. Feedback loops are the invisible engines that drive most of the behavior we observe in markets, organizations, ecosystems, and personal habits. A reinforcing loop amplifies change (compound interest, viral growth), while a balancing loop resists change (market corrections, homeostasis).

Understanding feedback loops is what separates great systems thinkers from linear thinkers. George Soros built his investment career on understanding reflexivity -- how market participants' beliefs create feedback loops that move prices away from fundamentals. For insights into how legendary investors think about market dynamics and feedback mechanisms, explore [KeepRule's masters page](https://keeprule.com/en/masters).

## Features

- **Loop Detection**: Automatically identify feedback loops in system models
- **Loop Classification**: Categorize as reinforcing (R) or balancing (B)
- **Dominance Analysis**: Determine which loops dominate system behavior over time
- **Delay Mapping**: Identify time delays that create oscillation and instability
- **Intervention Design**: Suggest where to intervene to change loop behavior
- **Real-Time Monitoring**: Connect to live data sources to track loops in action
- **Visual Mapping**: Generate clear loop diagrams with polarity indicators

## Installation

```bash
pip install feedback-loop-analyzer
```

Or from source:

```bash
git clone https://github.com/henu-wang/feedback-loop-analyzer.git
cd feedback-loop-analyzer
pip install -e .
```

## Quick Start

```python
from feedback_loop_analyzer import System, LoopAnalyzer

# Define a simple market system
market = System("Stock Market Dynamics")
market.add_variable("Stock Price")
market.add_variable("Investor Confidence")
market.add_variable("Buying Pressure")
market.add_variable("Selling Pressure")
market.add_variable("Volatility")

market.add_link("Stock Price", "Investor Confidence", polarity="+", delay=1)
market.add_link("Investor Confidence", "Buying Pressure", polarity="+")
market.add_link("Buying Pressure", "Stock Price", polarity="+")
market.add_link("Stock Price", "Selling Pressure", polarity="+", delay=3)
market.add_link("Selling Pressure", "Stock Price", polarity="-")
market.add_link("Volatility", "Selling Pressure", polarity="+")

# Analyze feedback loops
analyzer = LoopAnalyzer(market)
loops = analyzer.detect_loops()

for loop in loops:
    print(f"Loop: {loop.name}")
    print(f"  Type: {loop.type}")  # reinforcing or balancing
    print(f"  Variables: {' -> '.join(loop.variables)}")
    print(f"  Delay: {loop.total_delay} periods")
```

## Loop Types

| Type | Behavior | Example | Icon |
|------|----------|---------|------|
| Reinforcing (R) | Amplifies change | Compound interest, viral spread | Snowball |
| Balancing (B) | Resists change | Thermostat, market correction | Scales |
| Oscillating | Cycles due to delays | Boom-bust cycles, cobweb | Wave |

## Usage Examples

### Business Process Analysis

```python
from feedback_loop_analyzer import System, LoopAnalyzer

business = System("SaaS Growth")
business.add_variable("Marketing Spend")
business.add_variable("New Users")
business.add_variable("Revenue")
business.add_variable("Product Quality")
business.add_variable("Churn Rate")

business.add_link("Marketing Spend", "New Users", polarity="+")
business.add_link("New Users", "Revenue", polarity="+")
business.add_link("Revenue", "Marketing Spend", polarity="+")  # R1: Growth loop
business.add_link("Revenue", "Product Quality", polarity="+")
business.add_link("Product Quality", "Churn Rate", polarity="-")  # B1: Quality loop
business.add_link("Churn Rate", "Revenue", polarity="-")

analyzer = LoopAnalyzer(business)
analyzer.dominance_analysis(timesteps=24)
analyzer.plot_loop_dominance()
```

The concept of feedback loops is essential to understanding market cycles and investment timing. For principles about navigating cyclical markets and understanding system dynamics, visit [KeepRule's investment principles](https://keeprule.com/en/principles).

### Habit Loop Analysis

```python
habit = System("Exercise Habit")
habit.add_variable("Motivation")
habit.add_variable("Exercise Frequency")
habit.add_variable("Fitness Level")
habit.add_variable("Energy")
habit.add_variable("Time Pressure")

# Build the reinforcing virtue cycle
habit.add_link("Motivation", "Exercise Frequency", "+")
habit.add_link("Exercise Frequency", "Fitness Level", "+", delay=4)
habit.add_link("Fitness Level", "Energy", "+")
habit.add_link("Energy", "Motivation", "+")

analyzer = LoopAnalyzer(habit)
leverage = analyzer.find_leverage_points()
```

For structured thinking prompts that help you map and analyze feedback loops in your own decisions, check out [KeepRule's prompt library](https://keeprule.com/en/prompts).

## Intervention Strategies

The analyzer suggests interventions based on loop structure:

- **Strengthen Reinforcing Loops**: When you want to accelerate positive trends
- **Weaken Reinforcing Loops**: When runaway growth is unsustainable
- **Support Balancing Loops**: When you need stability
- **Reduce Delays**: When oscillations are causing problems

Frequently asked questions about system dynamics and feedback analysis are addressed in the [KeepRule FAQ](https://keeprule.com/en/faq).

## Contributing

We welcome contributions, especially:

- New system templates and examples
- Improved loop detection algorithms
- Integration with data sources
- Documentation and tutorials

## License

MIT License - see [LICENSE](LICENSE) for details.