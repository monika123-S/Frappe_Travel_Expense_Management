### Etems

Travel Expense Management

### Installation

You can install this app using the [bench](https://github.com/frappe/bench) CLI:

```bash
cd $PATH_TO_YOUR_BENCH
bench get-app $URL_OF_THIS_REPO --branch main
bench install-app etems
```

### Contributing

This app uses `pre-commit` for code formatting and linting. Please [install pre-commit](https://pre-commit.com/#installation) and enable it for this repository:

```bash
cd apps/etems
pre-commit install
```

Pre-commit is configured to use the following tools for checking and formatting your code:

- ruff
- eslint
- prettier
- pyupgrade
### CI

This app can use GitHub Actions for CI. The following workflows are configured:

- CI: Installs this app and runs unit tests on every push to `develop` branch.
- Linters: Runs [Frappe Semgrep Rules](https://github.com/frappe/semgrep-rules) and [pip-audit](https://pypi.org/project/pip-audit/) on every pull request.


### License

mit

Travel Expense Management:

Flow of the system 
Employee creates Travel Request in advance so that the superior approves the request and would also able to get advance amount if required and then after the travel the employee makes the expense claim to get the  claimed about as from the company 


Let's see how this works in the actual business flow :
how empolyee creates Travel Request and with what data in the company :

frist,we want personal informations about the employee  
Section 1: Personal Information
    Full name 
    Branch
    Job Title
    Department
    Phone number 
    Email address. 

Section 2 : Travel Details
Travel itinerary with:
Dates (start and end) 
Destinations
Reason for travel

Section 3: Accommodation and Transportation
stimated budget for expenses like:
Flights
Hotels
Daily Allowances

Section 4 : Support required from the company, such as:
Advance Amount if required


