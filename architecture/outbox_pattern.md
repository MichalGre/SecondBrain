# Outbox pattern

## Summary
It's a pattern that helps implement reliable messaging. So, it guarantees at "least once" delivery.
Consumer must guarantee idempotence on message receival. 

In this method domain events are not written to event bus. Instead, they are persisted in the database and after that job takes event from database and publish them. 

Idempotence - receiving duplicated messages has the same final effect on the system state as receiving one message. 

![image info](https://miro.medium.com/v2/resize:fit:720/format:webp/0*WUdjvJ6zsVqaKo8p.png)


## Resources:
- https://medium.com/design-microservices-architecture-with-patterns/outbox-pattern-for-microservices-architectures-1b8648dfaa27
- https://www.kamilgrzybek.com/blog/posts/the-outbox-pattern

:architecture: :patterns:
