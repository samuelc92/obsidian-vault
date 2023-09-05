- **Event**: the purpose is to alert other parts of a system that something occurred under a specific boundary. An event can be the result of command completion. Events have multiple consumers who reside under different boundaries. Events are represented in the past tense (EmailSent, OrderPlaced, PaymentReserved, etc.).
- **Commands**: the purpose is to invoke a behavior related to a business logic within a specific boundary. Commands have a single consumer. They are represented by a verb (SendEmail, PlaceOrder, ReserverPayment, etc.).

|          | Commands                  | Events                   |
|----------|---------------------------|--------------------------|
|Purpose   | Invoke Behavior           | Something Happened       |
|Ownership | Command Owned by Consumer | Event Owned by Publisher |
|Consumers | One Consumer              | Zero or Many Consumers   |
|Senders   | Many Senders              | Single Publisher         |
|Naming    | Verb                      | PastTense                |
