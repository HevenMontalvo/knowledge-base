
---
topic: Infrastructure / cloud
subtopic: Iac
tools: [Terraform]
---

# Essential Terraform Commands

| Command | Description | When to use it |
| :--- | :--- | :--- |
| **`terraform init`** | Initializes the working directory. Downloads providers (like AWS) and sets up the backend. | Run this first when starting a new project or after cloning one. |
| **`terraform fmt`** | Automatically reformats `.tf` code to follow canonical style and alignment. | **The "magic" command**: Use it to fix indentations and spacing automatically. |
| **`terraform validate`** | Checks whether the configuration is syntactically valid and internally consistent. | Use it after editing code to catch errors before attempting a deployment. |
| **`terraform plan`** | Generates an execution plan, showing what resources will be created, changed, or destroyed. | Use it to preview changes without affecting real infrastructure. |
| **`terraform apply`** | Executes the actions proposed in a Terraform plan to reach the desired state. | Use it when you are ready to deploy or update your resources in the cloud. |
| **`terraform destroy`** | Removes all remote objects managed by a particular Terraform configuration. | Use it to clean up environments and avoid unnecessary cloud costs. |
| **`terraform show`** | Provides a human-readable output of the current state or a plan file. | Use it to inspect the technical details of your deployed infrastructure. |
| **`terraform state list`** | Lists all resources currently tracked in the Terraform state file. | Use it to see exactly which resource IDs are under Terraform's control. |
| **`terraform output`** | Extracts the value of output variables from the state file. | Use it to quickly get IPs, DNS names, or IDs after a successful apply. |
| **`terraform force-unlock`** | Manually releases a stuck state lock on the current workspace. | Only use it if a process crashed and others are blocked from deploying. |

---

### Pro-Tips for your Workflow:

* **The `fmt` Habit**: you'll find `terraform fmt` incredibly helpful. It aligns `=` signs and braces perfectly. Run it every time you save.
* **Standard Cycle**: The professional DevOps workflow is always: `init` -> `fmt` -> `validate` -> `plan` -> `apply`.
* **Plan Symbols**: Always pay attention to the symbols in the plan output:
    * **`+` green**: Resource will be created.
    * **`~` yellow**: Resource will be updated in-place.
    * **`-` red**: Resource will be destroyed (Exercise caution!).