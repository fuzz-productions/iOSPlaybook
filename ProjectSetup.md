## Project Setup

### Values 
Projects should be set up in a way that allows team members to: 
- Understand major conventions of the project
- Navigate through the project quickly and logically
- Locate resources pertaining to a project quickly
- Build and deploy easily

### Rule of Thumb
	
As soon as a project is created that is intended to be the repository for a client project, that project should be setup correctly. 
	
Moving quickly at the beginning of projects is important, but speed should not come at the expense of inefficiencies later on. As a project gets more complex, issues with its initial setup compound.

---

<details><summary>ReadMe</summary><p>

### Location: 

ReadMe’s exist in a project’s repository

### Values

* A ReadMe: 
- Should be short. Long ReadMe’s are not read. 
* Should include: 
- Installation instructions
- Links to Technical Documentation
- Links to major project conventions
* May also include: 
- Links to pods used within the project
- Update the ReadMe with new changes

</p></details>

---

<details><summary>Technical Documentation</summary><p>


### Location
Depending on the project, Technical Documentation exists in Google Docs or in Confluence. 

### Values

- Technical Documentation: 
- Should be project specific 
- Generally includes: 
- API information
- Does Not Include: 
- Code examples (These should be documented inline, or linked to within the ReadMe)

---
### Examples
[m360](https://gitlab.fuzzhq.com/ios-project/m360/blob/dev/README.md)

---

</p></details>

---

<details><summary>Project Structure</summary><p>


### Values
- Project Structure should have: 
- .gitignore
- A reasonable, organized Directory Structure
- Continuous Integration
- Swift Linting (or something of the like)
- Documentation via Jazzy

### Required Module
Fazu https://gitlab.fuzzhq.com/ios-tools/fazu-ci 

Fazu provides: 
- Continuous Integration
- Building and deployment from console
- Documentation via Jazzy
- Provisioning

### Recommended Module

Plato https://gitlab.fuzzhq.com/ios-labs/plato

Plato provides: 
- .gitignore 
- Directory Structure
- Swift Lint

</p></details>

---

<details><summary>Recommended Project Checklist</summary><p>

- [ ] **Create a new project**
	* Recommendation: Use Plato https://gitlab.fuzzhq.com/ios-labs/plato
	- [ ] .gitignore
	- [ ] Swift Lint
	- [ ] Directory Structure
	- [ ] Provisioning

- [ ] **Push to GitLab Repository**

- [ ] **Create or Update ReadMe**
	- [ ] Installation Instructions
	- [ ] Links to Technical Documentation
	- [ ] Links to major project conventions
	- [ ] Links to Pods 

- [ ] **Create Technical Documentation (via confluence or Google Docs)**
	- [ ] API Information

- [ ] **Integrate with Fazu**
Fazu https://gitlab.fuzzhq.com/ios-tools/fazu-ci 

- [ ] **Implement a build process for development/production**
	- See m360 for details.
	- TODO: Add more details on m360 after Noah's presentation.

</p></details>

---
