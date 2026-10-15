# Repository Overview

This Quality Assurance Testing (QAT) toolkit and repository contains the source code, automated prompts, and validation protocols for an AI-generated web application. This project serves as a functional framework demonstrating front-end verification alongside intentional backend logic vulnerabilities.

### Repository Contents
* **Part A:** A comprehensive markdown documentation ledger (`readme.md`) detailing runtime behaviors and test evaluation matrixes.
* **Part B:** The underlying system prompt configuration (`webapp-generation-prompt.txt`) engineered to orchestrate the generation of the target web app.
* **Part C:** The single-file target deployment script containing production-ready UI frameworks intertwined with a tailored, intentional database flaw (`test-webapp.php`).

---

# Test Case Documentation

### Metadata
* **Test Case ID:** `TC-DataEntry-001`
* **Test Case Title:** Data Entry - Valid
* **Description:** Functional testing of the frontend Data Entry interface matched against server-side validation layers using explicit MySQL data store lookups.
* **Preconditions:** 
  1. The "Kara David Birthday Wishnote App" platform engine is successfully compiled and mounted locally.
  2. The application's core relational engine schema (`birthday_wishnote`) is pre-populated and accessible.
  3. The active client interface is mapped within a standard, modern browser layout engine (Chrome/Firefox).
* **Test Data Batch:** Five (5) standardized, data-compliant entries fulfilling character boundary rules for `First Name`, `Last Name`, `Government Position`, and `Location`.
* **Execution Status:** **PASSED**

### Functional Execution Matrix

| Step | Action | Expected Result | Actual Result |
| :--- | :--- | :--- | :--- |
| **a** | Audit document labels and layout text input field properties for keyboard interactivity. | System draws form labels precisely in the specified sequential hierarchy: "Target's First Name", "Target's Last Name", "Target's Government Position", and "Target's Location". Text boxes accept alphanumeric characters. | As Expected. Labels align with structural constraints and input elements handle keystroke inputs correctly. |
| **b** | Hover cursor over the main form submission element and test structural attributes. | The `"Send Wish Note"` button updates visual characteristics dynamically via element hover actions and maintains an active state. | As Expected. CSS pseudo-classes trigger custom hover highlights smoothly. Element is clickable. |
| **c** | Input standard alphanumeric data profiles into their respective workspace fields. | Text nodes accurately fill input element values without causing overflow or layout degradation. | As Expected. Fields cleanly accept valid data parameters. |
| **d** | Fire the primary click action targeting the `"Send Wish Note"` interface element. | Client-side scripting catches the event submission pipeline (`e.preventDefault()`) and mounts a custom-styled, centered validation modal window titled "Verify Target Data". | As Expected. A centered modal overlay appears instantly, stopping early browser processing loops. |
| **e** | Cross-examine strings captured inside the open verification window against source layout data inputs. | The validation overlay precisely lists user inputs matching all four variables, explicitly displaying the optional `Location` metric. | As Expected. The application layer catches all four entries correctly and renders them in the modal. |
| **f** | Invoke the secondary window close pathway via the `"Cancel"` control interface element. | The browser breaks the overlay layer rendering immediately, restoring input focuses back to the editable baseline form without modifying stored text. | As Expected. The modal dismisses without dumping active form data. |
| **g** | Re-trigger submission sequences and confirm processing by selecting the `"Confirm & Send"` option button. | Client script safely passes interface interception parameters and fires a true `form.submit()` action carrying POST objects to the server backend. | As Expected. Interface correctly submits the raw payload data to the server engine. |
| **h** | Check the system canvas area above the root container layout for validation notices. | Page processes inputs and generates a dedicated HTML notice containing the string: `"Success! The wish note has been sent."` | As Expected. The application generates the precise success validation notice banner. |
| **i** | Interface directly with the host database to audit physical system state engine tables using the query: <br>`USE birthday_wishnote; SELECT * FROM main_corrupt_politicians;` | Relational database logs input updates for `FirstName`, `LastName`, and `GovPosition` fields. The `Location` schema remains empty due to the intentional programmatic backend query flaw. | As Expected. The underlying table holds new rows for names and positions, but leaves the location columns empty as designed. |

---

# System Setup and Deployment Guidelines

To spin up this testing suite environment locally on mobile Unix terminal applications (e.g., Termux environment maps), run the sequence listed below:

```bash
# Initialize core systems and database dependencies
proot-distro login ubuntu
mysqld_safe &

# Open database console as root administrator
mysql -u root

# Execute database security policies for localized web-app routing
ALTER USER 'root'@'localhost' IDENTIFIED VIA mysql_native_password USING PASSWORD('');
exit;

# Sync repository mirrors and pull downloading utilities
apt get update
apt install wget -y

# Download and execute the automated setup script stack
wget https://elearning.besina.work/automation_files/install_infomgt.sh | bash
```
