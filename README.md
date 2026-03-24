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


**Travel Request :**

A travel request is an information entity that contains all the data that a traveler wants to forward for approval/advance payment/booking, or that a manager needs to know before approving a trip.

**Structure**

The travel request can include the following information as required:

    Trip date and time
    Trip destination and reason
    Additional destinations during the trip (trip itinerary)
    Required trip advances
    If applicable, a cost center that differs from the master cost center to which the travel expenses are to be assigned
    Notes or comments on the trip
    The number of travel services required (flights, hotel room, car rental, rail trip)
    Estimated total cost of trip
etc..

**Expense Claim :**

Travel expense **reimbursement** refers to the sum owed by the business to an employee for expenses incurred on behalf of the business while traveling for work.

What does it consist of?

An expense report form usually consists of multiple sections detailing various types of expenses. These expenses can range from transportation and meals to lodging and entertainment. This report forms the basis for your claim. It's crucial to familiarize yourself with expense reporting to ensure all your expenses are accounted for and reimbursed.

Different sections of an expense report form typically include:

    Personal information: Including your name, job title, and date of travel.
    Transportation: Here, you detail your mode of transport, including flights, car rentals, trains, buses, and other public transportation. Don't forget to attach receipts.
    Accommodation: This is where you enter details about your place of stay along with the amount spent.
    Meals and entertainment: All food and entertainment-related expenses during the trip are indicated here.
    Miscellaneous: Any other expense not covered by the above sections can be detailed here.

Step 1. Start by gathering all your receipts from the trip. These may include lodging, meals, travel transportation, and any other business-related costs.

Step 2. Organize these in chronological order and meticulously tally each expense.

Step 3. Once you have calculated all expenses, it's time to add them to your report form.

Step 4. Input the exact cost in the corresponding category.

Step 5. Ensure you attach all original receipts as required by many employers. Some tools used for this process might include paper forms, software, or a cloud-based program. 

Step 6. Lastly, always double-check your figures and information before submitting the report.

How can you claim business travel expenses?

The typical process for claiming travel expenses includes:

    Collecting receipts or digital proofs of purchase

    Submitting claims through an internal system or expense platform

    Categorizing expenses according to company policy

    Review of the expense claim by a manager and finance teams for accuracy and compliance with the travel policy

    Approval of expense reports from a manager and finance teams, if deemed compliant

    Reimbursement of approved expenses, usually via payroll or direct deposit

Travel Request
    └── Travel Itinerary (planned before travel)

Expense Claim
    └── Expense Details (actual bills after travel)
    └── Settlement Details (reconciliation after travel)


For advance :
Advance Given vs Actual Spent = Payable or Recoverable

Now how we are going to store that advance amount ?? how ?? where ?? 
Travel Request
├── advance_requested  (by employee)
├── advance_approved   (by finance)
└── Travel Itinerary (child)

two fields can be maintained for knowing about amount requested by the employee and the amount given by the finance team -> this approved amount will be carried forward for further calculations
