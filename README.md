# Paytm Labs DBA Challenge

## Data modelling

Design appropriate MySQL database tables that can provide hypothetical wallet service. For simplicity, this wallet service will only support 1-way money transfers from one wallet to another.

1. Draw appropriate diagrams for your design proposal. Feel free to use any tool of your choice to express the table schemas. If you don't have a preference, [dbdiagram.io](https://dbdiagram.io/) is a good choice.
2. Explain any key schema design decisions. Feel free to include any non-schema design decisions to support your overall design. If you've made any assumptions, remember to include them here.

Make sure to meet the following minimum requirements. You're free to cover additional data or perform additional optimizations as you see fit but those will only count as bonus points given that minimum requirements are met.

### Minimum data requirements

- Wallet
    - User ID
    - Balance
- Transaction
    - Payment ID
    - Source wallet ID
    - Destination wallet ID
    - Source order amount
    - Destination order amount
    - Source wallet balance
    - Destination wallet balance

### Minimum functional requirements and goals

- Needs to be:
    - Reliable
        - Less room for human error, the better.
        - Database setup needs to be fault-tolerant, if it impacts the schema design.
    - Scalable
        - Traffic will vary with several peaks throughout the day.
        - Target 1 second P99 latency.
        - Target up to 4,000 wallet transactions per second.
    - Maintainable
        - Needs to be operable. Expect the service to run for many years to come. Target at least 20 years.
        - Focus on simplicity unless it is a necessary evil.
        - Needs to be extensible. No major schema changes should be required in the future.

- Focus on write performance for the sake of simplicity. Any additional consideration for read traffic is a bonus.
