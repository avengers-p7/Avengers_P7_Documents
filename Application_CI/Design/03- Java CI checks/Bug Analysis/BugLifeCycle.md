# Bug Life Cycle in Software Development

| **Author**           | **Created On** | **Last Updated** | **Document Version** |
| -------------------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 30-01-2024     | 30-01-2024       | V1                   |

# Table of Contents

1. [Introduction](#introduction)
2. [What Is a Bug Life Cycle(Defect Life Cycle)?](#what-is-a-bug-life-cycle-defect-life-cycle)
3. [Defect/Bug Status](#defectbug-status)
4. [Stages of Bug Life Cycle in Testing](#stages-of-bug-life-cycle-in-testing)
5. [Contact Information](#contact-information)
6. [Resources and References](#resources-and-references)

***

## Introduction

### What Is a Bug Life Cycle(Defect Life Cycle)?

![image](https://github.com/avengers-p7/Documentation/assets/156056413/7b09e707-02fc-4192-a904-ce1f407b5f63)

Bug Life Cycle, also known as the defect life cycle, is the journey a bug takes from its discovery to resolution, either by being closed or rejected.

When a bug is spotted, the bug life cycle provides a structured process to guide its resolution. It's like a roadmap for addressing issues in the software. Not everyone on the team needs to fix a bug; different team members step in at various stages.

Think of it like this: Imagine you find a problem in the software. You report it, and then a series of steps kick in to make sure the issue gets fixed. This process is crucial for building and updating software programs.

In this bug life cycle, two key players are the tester and the developer. The tester finds or reviews the bug and passes it to the developer, who then comes up with a solution.

Now, let's talk about defect status – this is just a way of saying, "Where is the bug in the process right now?"

Understanding this bug life cycle helps teams communicate effectively and ensures that bugs get the attention they need.

### Defect/Bug Status

Bug Status is a quick snapshot of where a bug is in its life cycle. It tells us the current state of the issue, helping everyone stay on the same page and track progress efficiently during testing.

#### Stages of Bug Life Cycle in Testing

| **Stage**       | **Description**                                                                                                          |
| --------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **New**          | A new defect is registered and posted for the first time. The tester provides a detailed defect/bug report to the development team. |
| **Assigned**     | The tester's lead authorizes the bug and assigns it to the developer team. It can be directly assigned to the developer or to the Dev Lead for further approval. |
| **Open**         | The developer analyzes and resolves the defect. Involves detecting and rectifying errors in testing and code. If the defect is deemed inappropriate, it may be moved to 'Deferred' or 'Rejected'. |
| **Fixed**        | A developer assigns a "Fixed" status to a bug after making a relevant code change and verifying the change. The defect is ready for testing in the upcoming build. |
| **Test**         | The defect is fixed and ready for testing. The test is performed to verify that the bug is fixed. |
| **Verified**     | The tester re-tests the bug after it's fixed. If the bug is not reproduced, a "Verified" status is assigned. |
| **Closed**       | If the bug is resolved, the tester allocates the "Closed" status. Indicates that the bug is fixed, tested, and validated. |
| **Reopen**       | In certain scenarios where the bug persists after resolution, the tester assigns a "Reopen" status. The bug goes through the same life cycle again. |
| **Duplicate**    | If the same bug is reported twice, the status is changed to "Duplicate," and the defect is rejected. |
| **Deferred**     | The tester/bug triage team assigns a "Deferred" state if the bug is not of key priority and is expected to be resolved in the forthcoming release, or if the customer intends to modify the requirement. High-priority bugs cannot be deferred. |
| **Rejected**     | If the developer perceives that the defect is due to misinterpretation or is not genuine, they will assign a "Rejected" state. Reasons for rejection may include it not being a defect, duplicate defect, or non-reproducible. |
| **Cannot be fixed** | The developer assigns a "Can't be fixed" state to the defect under cases like unsupported technology, high cost of fixing the bug, or lack of necessary skills. |
| **Not a defect** | If the defect doesn’t impact other functions of the software, it is assigned a ‘NOT A DEFECT’ state. Ultimately, it is ‘Rejected’. |

## Contact Information

|    Name                                   | Email Address                    |
|-------------------------------------------|----------------------------------|
| **[Parasharam Desai](https://github.com/Parasharam-Desai)** | parasharam.desai.snaatak@mygurukulam.co |

***

# Resources and References

| **Description**                 | **References**                                                           |
|----------------------------------|--------------------------------------------------------------------------|
| Documentation Template          | [Application Template](https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template) |
| Bug Life Cycle - Katalon Blog    | [Bug Defect Life Cycle](https://katalon.com/resources-center/blog/bug-defect-life-cycle) |
| Understanding Bug Life Cycle     | [Bug Life Cycle Article](https://testsigma.com/blog/bug-life-cycle/#What_is_BugDefect) |
