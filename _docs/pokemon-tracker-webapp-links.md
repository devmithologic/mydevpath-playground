# Pokemon Card Collection Tracker - Learning Resources Guide

## Foundation Technologies

### .NET and C# Backend Development

**Microsoft Official Documentation**
The official Microsoft documentation serves as your primary reference throughout the learning process. Start with the fundamentals and gradually work toward advanced concepts like dependency injection and middleware patterns.

- [ASP.NET Core Web API Tutorial](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-web-api) - Essential starting point for understanding .NET Web API architecture
- [C# Programming Guide](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/) - Comprehensive language reference covering modern C# features
- [ASP.NET Core Fundamentals](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/) - Deep dive into middleware, dependency injection, and configuration patterns
- [Entity Framework Core](https://docs.microsoft.com/en-us/ef/core/) - While we're using MongoDB, understanding EF Core patterns helps with general data access concepts

**Supplementary Learning Resources**
These resources provide practical examples and real-world patterns that complement the official documentation. They often include common pitfalls and best practices learned from production experience.

- [Clean Architecture with .NET Core](https://github.com/jasontaylordev/CleanArchitecture) - Excellent project template showing professional .NET architecture patterns
- [.NET Application Architecture Guides](https://dotnet.microsoft.com/en-us/learn/dotnet/architecture-guides) - Microsoft's architectural guidance for different application types
- [Tim Corey's C# Tutorials](https://www.youtube.com/c/IAmTimCorey) - Practical, project-based learning with industry best practices

### MongoDB Database Development

**MongoDB Official Resources**
MongoDB's documentation excels at explaining document-oriented thinking, which differs significantly from relational database patterns. Pay special attention to data modeling concepts and indexing strategies.

- [MongoDB Manual](https://docs.mongodb.com/manual/) - Comprehensive database reference covering all MongoDB concepts
- [MongoDB University](https://university.mongodb.com/) - Free, structured courses including "MongoDB for Developers" and "Data Modeling"
- [MongoDB .NET Driver Documentation](https://docs.mongodb.com/drivers/csharp/) - Essential for understanding how to integrate MongoDB with your .NET application
- [Data Modeling Introduction](https://docs.mongodb.com/manual/core/data-modeling-introduction/) - Critical for understanding document database design patterns

**Practical MongoDB Learning**
These resources focus on real-world scenarios and performance considerations that become important as your application scales.

- [MongoDB Best Practices](https://www.mongodb.com/developer/products/mongodb/mongodb-schema-design-best-practices/) - Schema design patterns and anti-patterns
- [MongoDB Performance Tuning](https://docs.mongodb.com/manual/administration/analyzing-mongodb-performance/) - Indexing strategies and query optimization

## Infrastructure and DevOps Technologies

### Docker Containerization

**Docker Official Documentation**
Docker's learning path progresses logically from basic container concepts to complex orchestration scenarios. Focus initially on Dockerfile best practices and later expand to compose and networking.

- [Docker Get Started Guide](https://docs.docker.com/get-started/) - Hands-on introduction to containerization concepts
- [Dockerfile Best Practices](https://docs.docker.com/develop/dev-best-practices/) - Security and optimization patterns for production containers
- [Docker Compose Documentation](https://docs.docker.com/compose/) - Essential for local development environment management
- [Docker Networking](https://docs.docker.com/network/) - Understanding container communication patterns

**Advanced Docker Learning**
These resources cover production deployment patterns and security considerations that are crucial for SRE roles.

- [Docker Security](https://docs.docker.com/engine/security/) - Security best practices for container deployments
- [Multi-stage Builds](https://docs.docker.com/develop/dev-best-practices/#how-to-keep-your-images-small) - Optimization techniques for smaller, more secure images

### Amazon Web Services (AWS)

**AWS Official Training and Documentation**
AWS documentation can be overwhelming initially, so follow a structured learning path that builds from basic concepts to advanced services. The Well-Architected Framework provides excellent architectural guidance.

- [AWS Getting Started Resource Center](https://aws.amazon.com/getting-started/) - Structured learning paths for different use cases
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/) - Fundamental principles for building reliable, secure, and efficient systems
- [Amazon ECS Documentation](https://docs.aws.amazon.com/ecs/) - Container orchestration service for running your Docker containers
- [AWS IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) - Security and access management patterns
- [Amazon DocumentDB](https://docs.aws.amazon.com/documentdb/) - MongoDB-compatible managed database service

**Practical AWS Learning**
These hands-on resources provide real-world scenarios and cost optimization strategies that are valuable for both development and SRE roles.

- [AWS Hands-On Tutorials](https://aws.amazon.com/getting-started/hands-on/) - Step-by-step guides for common deployment scenarios
- [AWS Architecture Center](https://aws.amazon.com/architecture/) - Reference architectures and case studies
- [AWS Cost Optimization](https://aws.amazon.com/aws-cost-management/aws-cost-optimization/) - Essential knowledge for production deployments

## CI/CD and Automation

### GitHub Actions

**GitHub Actions Official Documentation**
GitHub Actions documentation excels at explaining workflow concepts and provides excellent examples for common deployment scenarios. Start with basic workflows and progress to complex deployment pipelines.

- [GitHub Actions Quick Start](https://docs.github.com/en/actions/quickstart) - Introduction to workflow automation concepts
- [Workflow Syntax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions) - Complete reference for creating deployment pipelines
- [GitHub Actions for .NET](https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-net) - Specific patterns for .NET application deployment
- [Deploying to AWS](https://docs.github.com/en/actions/deployment/deploying-to-cloud-providers/deploying-to-amazon-elastic-container-service) - Integration patterns with AWS services

**DevOps Best Practices**
These resources cover broader DevOps concepts that complement your technical GitHub Actions knowledge and are essential for SRE roles.

- [The DevOps Handbook](https://itrevolution.com/the-devops-handbook/) - Fundamental DevOps principles and practices
- [Site Reliability Engineering Book](https://sre.google/sre-book/table-of-contents/) - Google's approach to running production systems at scale

## Frontend Technologies

### Modern JavaScript Development

**Mozilla Developer Network (MDN)**
MDN provides the most comprehensive and accurate JavaScript documentation available. Focus on modern ES6+ features and asynchronous programming patterns that are essential for API integration.

- [JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide) - Comprehensive language reference with modern best practices
- [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) - Essential for making HTTP requests to your backend API
- [JavaScript Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises) - Critical for handling asynchronous operations
- [DOM Manipulation](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) - Understanding how to dynamically update your user interface

**Modern JavaScript Frameworks and Tools**
While the project uses vanilla JavaScript initially, understanding these concepts helps with scaling frontend complexity and demonstrates broader knowledge.

- [Alpine.js Documentation](https://alpinejs.dev/) - Lightweight framework for adding reactivity to HTML
- [Tailwind CSS](https://tailwindcss.com/docs) - Utility-first CSS framework for rapid UI development

## Authentication and Security

### JWT and Security Best Practices

**Authentication Concepts**
Understanding authentication and authorization patterns is crucial for backend development and demonstrates security awareness that employers value highly.

- [JWT Introduction](https://jwt.io/introduction/) - Understanding JSON Web Tokens and stateless authentication
- [ASP.NET Core Authentication](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/) - Implementation patterns for .NET applications
- [OWASP Top 10](https://owasp.org/www-project-top-ten/) - Essential security vulnerabilities every developer should understand
- [ASP.NET Core Security Best Practices](https://docs.microsoft.com/en-us/aspnet/core/security/) - Comprehensive security guidance for .NET applications

## Monitoring and Observability

### Application Performance Monitoring

**AWS CloudWatch and Monitoring**
Observability skills distinguish good developers from great ones and are essential for SRE roles. These resources teach you how to build systems that can be effectively monitored and debugged.

- [AWS CloudWatch Documentation](https://docs.aws.amazon.com/cloudwatch/) - Comprehensive monitoring and logging for AWS applications
- [Application Insights for .NET](https://docs.microsoft.com/en-us/azure/azure-monitor/app/asp-net-core) - While AWS-focused, understanding multiple monitoring approaches broadens your skills
- [Prometheus Monitoring](https://prometheus.io/docs/introduction/overview/) - Industry-standard open-source monitoring system

**Observability Best Practices**
These resources teach you how to design applications that provide meaningful insights into their operation and performance.

- [The Three Pillars of Observability](https://www.oreilly.com/library/view/distributed-systems-observability/9781492033431/) - Comprehensive guide to logs, metrics, and tracing
- [SRE Workbook](https://sre.google/workbook/table-of-contents/) - Practical guidance for implementing reliability practices

## Learning Strategy and Timeline

### Recommended Learning Sequence

**Phase 1 Foundation (Weeks 1-2)**
Start with C# and .NET fundamentals, then immediately move to basic MongoDB integration. This gives you a working backend quickly, which maintains momentum and provides a foundation for testing other components.

**Phase 2 Core Development (Weeks 3-4)**
Focus on completing your core application logic with authentication and business features. This phase teaches you the most about backend development patterns and prepares you for technical interviews.

**Phase 3 Infrastructure (Weeks 5-6)**
Learn Docker and basic AWS deployment. This phase demonstrates your infrastructure capabilities and shows you can deploy applications professionally.

**Phase 4 Automation (Weeks 7-8)**
Implement CI/CD and monitoring. These skills differentiate you from developers who only write code but don't understand production operations.

### Interview Preparation Resources

**Technical Interview Preparation**
These resources help you articulate what you've learned and demonstrate your knowledge effectively during job interviews.

- [System Design Interview](https://github.com/donnemartin/system-design-primer) - Essential for backend and SRE roles
- [Coding Interview University](https://github.com/jwasham/coding-interview-university) - Comprehensive computer science fundamentals
- [Backend Developer Roadmap](https://roadmap.sh/backend) - Visual guide to backend development concepts and technologies

### Community and Support Resources

**Developer Communities**
Engaging with these communities helps you learn faster, get answers to specific questions, and understand current industry practices.

- [Stack Overflow](https://stackoverflow.com/) - Essential for troubleshooting specific technical issues
- [Reddit - r/dotnet](https://www.reddit.com/r/dotnet/) - Active community for .NET developers
- [Reddit - r/aws](https://www.reddit.com/r/aws/) - AWS community with practical tips and solutions
- [Dev.to](https://dev.to/) - Developer blogging platform with practical tutorials and experiences

This learning path provides comprehensive coverage of your chosen technology stack while building toward your career goals in backend and SRE engineering. The key to success lies in consistent daily practice and building real, working systems rather than just reading documentation. Each technology builds on the others, so the Pokemon Card Collection Tracker project serves as an excellent vehicle for integrating all these concepts into practical experience that employers value.