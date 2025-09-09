
# Welcome to the MyReadings Playground

This repository serves as the *meta-repository* for the **MyReadings** project, a full-stack application designed as a playground to explore and document modern software development practices - from modular architecture to deployment on container platforms like OpenShift.

The goal of this project is to serve as a practical, well-documented example of how to integrate various technologies to build, test, and deploy a complex application.

## Project Philosophy and Disclaimer

**This is, first and foremost, a study project.**

I haven't been a full-time software engineer for several years, so I'm a bit "rusty." I created `MyReadings` as an opportunity to get back in the game, study modern frameworks and concepts, and, most importantly, learn by doing.

Throughout this journey, I've used **AI as a coding and design companion**, much like an always-available pair programmer. I may have overused it at times, but it has been an integral part of the learning process.

For these reasons, the code and architectural choices may not always be perfect. **Feedback, suggestions, and contributions to improve the project are not just welcome - they are encouraged!**

## Goals and Roadmap

The idea is to use this project as a foundation to explore various concepts in modern software development and application refactoring.

### Current State

The project is currently a **modular monolith** with a Quarkus backend and a Vue.js frontend. All backend modules share a single PostgreSQL database, although they maintain separate schemas to ensure a clean logical separation of data.

### Future Plans (Work in Progress)

This is a non-exhaustive list of topics I'd like to explore using this project as a baseline. This is an ambitious project that I work on in my free time, so the roadmap is fluid and subject to change.

- **Architectural Evolution:**

  - **Refactoring to Microservices**: Extract one or more modules (e.g., `user` or `review`) into independent microservices.
  - **Exploring Data Stores**: Investigate the use of different, more suitable databases for specific domains (e.g., a graph database for user relationships).

- **Technology Topics (often with a focus on Red Hat technologies):**

  - **CI/CD**: Implement complete pipelines.
  - **Service Mesh**: Introduce Service Mesh to manage inter-service communication.
  - **Advanced Deployment Strategies**: Test advanced release patterns like Canary and Blue/Green.
  - **Observability**: Integrate a full observability stack.
  - **Advanced Testing**: Explore security, performance, and contract testing.
  - **Business Continuity**: Simulate failover scenarios and implement data protection strategies.

### How to Use This Project

I hope this repository can be used not only as a personal project but also as a foundation for creating **demos or Proof of Concepts (PoCs)** to showcase technologies (not necessarily from Red Hat) on an application that is slightly more complex than a simple "hello world."

## Project Structure: Multi-Repository Architecture

This project uses a multi-repository approach, where each core component of the system lives in its own dedicated Git repository. This meta-repository brings them all together using **Git Submodules**, allowing the entire ecosystem to be managed from a single point.

The three main components are:

- **`myreadings` (Backend)**: A **modular monolith** built with Quarkus (Java) that exposes the REST API for all business logic.
- **`myreadings_ui` (Frontend)**: A **Single-Page Application (SPA)** built with Vue.js and TypeScript, which serves as the user interface.
- **`myreadings_deploy` (Deploy)**: Contains all **Infrastructure as Code (IaC)** configuration, including Docker Compose files, database initialization scripts, and Ansible playbooks for provisioning.

## Getting Started

To start working with the project, you need to clone this repository along with all its submodules.

### Prerequisites

Ensure you have the following tools installed on your machine:

- [Git](https://git-scm.com/ "null")
- [Docker and Docker Compose](https://www.docker.com/ "null")
- [Java 21 (or higher)](https://www.oracle.com/java/ "null")
- [Node.js 18 (or higher)](https://nodejs.org/ "null") and npm

### Cloning the Project

Run this command to clone the repository and automatically initialize all submodules in one step:

`git clone --recurse-submodules <URL_of_this_repository>`

If you have already cloned the repository without the submodules, you can fetch them with:

`git submodule update --init --recursive`

## Development Workflows

The project is designed to support multiple development and deployment workflows. For detailed instructions, please refer to the `README` files in the individual repositories.

- [**Deployment instructions in `myreadings_deploy/README.md`**](https://github.com/too-common-name/myreadings_deploy "null")
- [**Backend development instructions in `myreadings/README.md`**](https://github.com/too-common-name/myreadings "null")
- [**Frontend development instructions in `myreadings_ui/README.md`**](https://github.com/too-common-name/myreadings_ui "null")
