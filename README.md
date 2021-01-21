# Paytm Labs DBA Challenge

## Data modelling

Design appropriate MySQL database tables that can provide hypothetical payment service. This payment service will only support simple payments from users to merchants between internal wallets.

1. Draw appropriate diagrams for your design proposal. Feel free to use any tool of your choice to express the table schemas. If you don't have a preference, [dbdiagram.io](https://dbdiagram.io/) is a good choice.
2. Explain any key schema design decisions. Feel free to include any non-schema design decisions to support your overall design. If you've made any assumptions, remember to include them here.

Make sure to meet the following minimum requirements. You're free to cover additional data or perform additional optimizations as you see fit but those will only count as bonus points given that minimum requirements are met.

### Minimum data requirements 

- User
    - Name
    - Mobile number
    - Email
- Merchant
    - Name
    - Address
    - Email
    
- Payment
    - Order (Needs to be identifiable)
    - State (One of: Created, Completed, Failed)
    - Payer wallet (Needs to be identifiable)
    - Receiver wallet (Needs to be identifiable)
- Order
    - User (Needs to be identifiable)
    - Merchant (Needs to be identifiable)
    - Order amount/price
    - Payment date
    
- Wallet
    - Type (One of: User, Merchant)
    - User or Merchant (Needs to be identifiable)
    - Balance
- Transaction
    - Payment (Needs to be identifiable)
    - Source wallet (Needs to be identifiable)
    - Destination wallet (Needs to be identifiable)
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
        - Target up to 4,000 payment transactions per second.
    - Maintainable
        - Needs to be operable. Expect the service to run for many years to come. Target at least 20 years.
        - Focus on simplicity unless it is a necessary evil.
        - Needs to be extensible. No major schema changes should be required in the future.
        
- Focus on write performance for the sake of simplicity. Any additional consideration for read traffic is a bonus.
