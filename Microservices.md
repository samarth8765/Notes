Before jumping on microservices we should first learn what is a Monolith architecture.

## Monolith architecture
- All components are part of a single unit.So for example if we are devolping an E-commerce website then different feature like user-auth, product-catalog, shopping-cart, payment all comes under one unit of code.

- App must be written with one tech stack.

- If in the above example we have to update the payment gateway option, we must redeploy the entire application.

- Challenges of monolithic architecture
    - App is too large and complex.
    - Parts are more tangled into each other.
    - High infrastructure cost.

- To overcome above problem we need Microservices Architecture.

# Microservices
- Micro Service is an architecture that allows the developers to develop and deploy services independently. Each service running has its own process and this achieves the lightweight model to support business applications.

1. Highly maintainable and testable
2. Loosely coupled
3. Independently deployable
4. Organized around business capabilities
5. Owned by a small team

- After knowing what microservices are let us answer some queries related to microservices.
    - How to break down the application ?
        - Split based on business functionalities.
        - 1 service for 1 specific job.

    - How do they communicate ?
        - Communicate via API calls (synchronous).
        - Communication via Message Broker (async).
        - Communication via Service Mesh (???).

    - How do we manage the code ?
        - Their are two ways in which we can manage our code:
        1. Monorepo - Using 1 git repository that contains many projects. Makes the code management and development easier .
        2.  Polyrepo - Using multiple git repository.


- Microservices developed new challenges.
    - It adds a complexity just by the fact that it is a distributed system.
    - Difficult to maintain microservices when they are large in numbers.
    - Tools are being developed to tackle these challenges like kubernetes.


                                           