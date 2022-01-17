# What is DevOps

Plan -> Build -> Continuous Integration -> Deploy -> Operate -> Continuous Feedback ... -> Plan

OODA (Observe, Orient, Decide, Act) loop.

## KPIs

### Faster outcomes

- **Deployment Frequency.** Increasing the frequency of deployments is often a critical driver in DevOps Projects.
- **Deployment Speed.** It is necessary to reduce the time that they take.
- **Deployment Size.** How many features, stories, and bug fixes are being deployed each time?
- **Lead Time.** How long does it take from the creation of a work item until it is completed?

### Efficiency

- **Server to Admin Ratio.** Are the projects reducing the number of administrators required for a given number of servers?
- **Staff Member to Customer Ratio.** Is it possible for fewer staff members to server a agiven number of customers?
- **Application Usage.** How busy is the application?
- **Application Performance. Is the application performance improving or dropping? (Based upon application metrics)?

### Quality and security

- **Deployment failure reates** How often do deployments (or applications) fail?
- **Application failure rates.** How often do application failures occur, such as configuration failures, performance timeouts, and so on?
- **Mean time to recover.** How quicly can you recover from a failure?
- **Bug report rates** You do not want customers finding bugs in your code. Is the amount they are seeing increasing or lowering?
- **Test pas rates.** How well is your automated testing working?
- **Defect escape rate.** What percentage of defects are being found in production?
- **Availability** What percentage of time is the application tryly available for customers?
- **Service level agreement achievement.** Are you meeting your service level agreements (SLAs)?
- **Mean time to detection** If ther is a failure, how long does it take for it to be detected?

### Culture

- **Employee moreale. Are employees happy with the transformation adn where the organization is heading?
- **Retention rates** Is the organization losing staff?

## Agile development practices

[Waterfall vs Agile comparison](https://docs.microsoft.com/en-gb/learn/modules/describe-team-structures/2-explore-agile-development-practices)

[12 Principles Behind the Agile Manifesto](https://docs.microsoft.com/en-gb/learn/modules/describe-team-structures/3-explore-principles-of-agile-development)

[Agile Manifesto](https://www.agilealliance.org/agile101/the-agile-manifesto/)

## DevOps tools

### Azure DevOps

Azure DevOps is a Software as a service (SaaS) platform from Microsoft that provides an end-to-end DevOps toolchain for developing and deploying software.

It also integrates with the most-leading tools on the market and is an excellent option for orchestrating a DevOps toolchain.

Azure DevOps includes a range of services covering the complete development life cycle.

- Azure Boards: agile planning, work item tracking, visualization, and reporting tool.
- Azure Pipelines: a language, platform, and cloud-agnostic CI/CD platform-supporting containers or Kubernetes.
- Azure Repos: provides cloud-hosted private git repos.
- Azure Artifacts: provides integrated package management with support for Maven, npm, Python, and NuGet package feeds from public or private sources.
- Azure Test Plans: provides an integrated planned and exploratory testing solution.
  
Also, you can use Azure DevOps to orchestrate third-party tools.

### GitHub

GitHub provides a range of services for software development and deployment.

- **Codespaces:** Provides a cloud-hosted development environment (based on Visual Studio Code) that can be operated from within a browser or external tools. Eases cross-platform development.
- **Repos:** Public and private repositories based upon industry-standard Git commands.
- **Actions:** Allows for the creation of automation workflows. These workflows can include environment variables and customized scripts.
- **Artifacts:** The majority of the world's open-source projects are already contained in GitHub repositories. GitHub makes it easy to integrate with this code and with other third-party offerings.
- **Security:** Provides detailed code scanning and review features, including automated code review assignment.

### Explore an authorization and access strategy

Azure DevOps Services uses enterprise-grade authentication. To protect and secure your data, you can use:

- Microsoft account.
- GitHub account.
- Azure Active Directory (Azure AD).
Tools like Visual Studio and Azure DevOps natively support the use of Microsoft Accounts and Azure AD. Eclipse can also support this form of authentication if you install a Team Explorer Everywhere plug-in.

[Details here](https://docs.microsoft.com/en-gb/learn/modules/migrate-to-devops/4-explore-authorization-access-strategy)

#### Personal access tokens (PAT)

Use personal access tokens (PAT) for tools that do not directly support Microsoft accounts or Azure AD for authentication. Also, if you want them to integrate with Azure DevOps.

#### Security groups

Azure DevOps is pre-configured with default security groups. Default permissions are assigned to the default security groups. But you can also configure access at the organization level, the collection level, and the project or object level.

In the organization settings in Azure DevOps, you can configure app access policies. Based on your security policies, you might allow alternate authentication methods, enable third-party applications to access via OAuth, or even allow anonymous access to some projects.

For even tighter control, you can set conditional access to Azure DevOps. It offers simple ways to help secure resources when using Azure Active Directory for authentication.

#### Multifactor authentication

Conditional access policies such as multifactor authentication can help to minimize the risk of compromised credentials.

As part of a conditional access policy, you might require:

- Security group membership.
- A location or network identity.
- A specific operating system.
- A managed device, or other criteria.

### Explore DevOps foundational practices

Version control is essential for all software development projects and is vital at large businesses and enterprises.

Enterprises have many stakeholders. For example:

- Distributed teams.
- Strict processes and workflows.
- Siloed organizations.
- Hierarchical organizations.

[Summary view here](https://docs.microsoft.com/en-gb/learn/modules/introduction-to-source-control/2-explore-devops-foundational-practices)

## Source Control

[Benefits of source control](https://docs.microsoft.com/en-gb/learn/modules/introduction-to-source-control/4-explore-benefits-of)

- [Centralized source control](https://docs.microsoft.com/en-gb/learn/modules/describe-types-of-source-control-systems/2-understand-centralized) Working with a centralized source control system, your workflow for adding a new feature or fixing a bug in your project will usually look something like this:
  - Get the latest changes other people have made from the central server.
  - Make your changes, and make sure they work correctly.
  - Check in your changes to the main server so that other programmers can see them.

- [Distributed source control](https://docs.microsoft.com/en-gb/learn/modules/describe-types-of-source-control-systems/3-understand-distributed)


