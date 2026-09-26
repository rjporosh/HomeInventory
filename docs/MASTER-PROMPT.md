Build a prototype offline-first web app called “Home Inventory”.

1. Core Goal

Create a practical personal household cash, shopping, inventory and daily-expense tracking system.

This is a prototype, not an enterprise application.

Technology constraints:

- Single "index.html"
- Vanilla HTML + CSS + JavaScript only
- No React
- No Angular
- No Vue
- No Node.js
- No backend
- No database server
- Offline-first
- Must work without internet after loading the app
- Use IndexedDB for persistent local storage
- Avoid Tailwind/CDN dependencies for the core UI
- Everything important must work offline
- Responsive/mobile-first UI
- Should work well on Android phones, tablets, laptops and desktop browsers
- Clean, modern, simple UI
- Bengali + English friendly
- Currency: Bangladeshi Taka (৳)

The application should feel like a combination of:

- household cash ledger
- shopping tracker
- daily expense tracker
- physical cash denomination tracker
- journey/transport tracker
- lightweight home inventory system
- Hishabi-style personal accounting

---

2. Dashboard

Create a dashboard showing:

- Current cash balance
- Total notes value
- Total coins value
- Total physical cash
- Today's total expense
- Current shopping sessions
- Today's shopping expense
- Today's transport expense
- Number of active/open sessions
- Recent transactions
- Quick actions:
  - Add Cash
  - Start Shopping
  - Add Expense
  - Add Journey
  - Add Income
  - View Reports
  - Export
  - Import/Merge

Use cards and compact mobile-friendly layouts.

---

3. Physical Cash / Denomination System

The user should be able to record exactly how many physical notes and coins they have.

Bangladesh denominations:

Notes

- ৳2
- ৳5
- ৳10
- ৳20
- ৳50
- ৳100
- ৳200
- ৳500
- ৳1000

Coins

- ৳1
- ৳2
- ৳5

Create a denomination table.

For every denomination:

- denomination
- quantity
- calculated total

Example:

৳100 × 5 = ৳500

Automatically calculate:

- Total notes
- Total coins
- Grand total physical cash

The user should NOT have to manually enter the total.

---

4. Advanced Note Information

Every note denomination should have an optional Advanced toggle.

Default:

- Advanced = OFF

When Advanced is OFF:

Only show:

- denomination
- quantity

Note condition should internally/default to:

- General

Torn note should default to:

- unchecked

When Advanced is ON, show:

Note condition

Options:

- New
- Medium Old
- Old
- General

Torn/Chhera note

Checkbox:

- Torn / Chhera Note

Note Number

Optional text/number field.

The user may enter serial/note number if desired.

Important:

The system should not force the user to enter note numbers.

The advanced section must remain hidden until the user enables Advanced.

---

5. Important Cash Reconciliation

Allow the user to create a cash snapshot.

Example:

"Morning Cash — 26 September 2026"

The user enters physical denominations.

System calculates:

৳1000 × 2 = ৳2000
৳500 × 3 = ৳1500
৳100 × 5 = ৳500
৳20 × 2 = ৳40

Total = ৳4040

Save this as a cash snapshot.

Allow multiple snapshots:

- Morning
- Before Shopping
- After Shopping
- Evening
- Custom

The user should be able to compare:

Cash before session
→ expenses
→ cash after session

and detect discrepancy.

---

6. Shopping Session

Create a concept called:

Shopping Session

Examples:

- First Shopping Today
- Morning Bazar
- Grocery Shopping
- Evening Market
- Pharmacy
- Super Shop

A day may contain multiple shopping sessions.

Example:

26 Sep:

1. Morning Bazar
2. Afternoon Grocery
3. Evening Pharmacy

Each session must be independent.

---

7. Start Shopping Session

When creating a shopping session, initially show a simple mode.

Required fields:

- Session name
- Date
- Start time
- Cash taken

Example:

Session:

"First Bazar Today"

Cash taken:

৳2000

The system records the starting cash.

---

8. Simple Shopping Mode

Default shopping mode should be SIMPLE.

The user should quickly add purchased items.

Each item can contain:

- Item name
- Price

Optional quick text format should also be supported.

For example:

Rice, 1090
Potato, 600
Rickshaw, 40

Or:

Rice - ৳1090
Potato - ৳600
Rickshaw - ৳40

The application should automatically calculate:

Total Shopping Expense

Example:

Rice = ৳1090
Potato = ৳600
Oil = ৳220

Total = ৳1910

---

9. Advanced Shopping Mode

Add an Advanced toggle.

Default:

Advanced = OFF

When OFF:

Keep the interface extremely simple.

When ON, show additional fields.

Shop information

- Shop name
- Shop phone
- Shop address

Item information

For every item:

- Item name
- Category
- Brand
- Unit
- Quantity
- Price per unit
- Total price
- Optional note
- Optional photo

Examples:

Rice
Unit: kg
Quantity: 5
Price/unit: ৳110
Total: ৳550

Oil
Unit: litre
Quantity: 2
Price/unit: ৳180
Total: ৳360

Automatically calculate item total.

---

10. Bill / Payment Reconciliation

Every shopping session should support:

- Total bill
- Amount paid
- Change/returned money

Example:

Bill = ৳850
Paid = ৳1000
Returned = ৳150

Automatically calculate.

Also allow:

- Payment method
  - Cash
  - Other

For prototype, Cash should be the primary method.

---

11. End Shopping Session

When the user returns home, provide:

End Session / Reconcile

Show:

Starting cash:
৳2000

Total expense:
৳1450

Expected remaining cash:
৳550

User enters:

Actual remaining cash:
৳550

System calculates:

Difference:
৳0

If actual cash is ৳500:

Difference:
-৳50

Show a clear discrepancy warning.

This is one of the most important features.

---

12. Journey / Transport Expense

A shopping session may contain multiple journeys.

Example:

Home → Bazar
Rickshaw ৳30

Bazar → Grocery
Rickshaw ৳20

Grocery → Home
Rickshaw ৳40

Create a Journey entry.

Simple mode:

- Transport type
- Cost

Examples:

Rickshaw — ৳20
CNG — ৳80
Bus — ৳30
Walking — ৳0

Advanced mode:

- Transport type
- From
- To
- Started at
- Ended at
- Date
- Time
- Cost
- Driver/contact optional
- Note

Automatically include journey/transport expense in the session total.

---

13. Daily Expense

Allow expenses outside shopping sessions.

Examples:

- Tea ৳20
- Mobile recharge ৳100
- Medicine ৳250
- Rickshaw ৳40
- Utility ৳1000

Each expense can contain:

- Name
- Amount
- Date
- Time
- Category
- Note

Advanced mode can provide:

- Vendor/shop
- Location
- Payment method
- Attachment/photo
- Note

---

14. Income / Cash Added

Allow the user to record money entering the household cash system.

Examples:

- Salary
- Freelancing
- Family contribution
- Returned money
- Other income

Fields:

- Source
- Amount
- Date
- Time
- Note

This should affect the cash ledger.

---

15. Categories

Create editable categories.

Default categories:

- Grocery
- Food
- Transport
- Medicine
- Household
- Utility
- Shopping
- Personal
- Entertainment
- Other

The user must be able to:

- Add category
- Rename category
- Delete category
- Disable category

Do NOT hard-code categories into the data model.

---

16. Household Inventory

The application should support a lightweight inventory.

Examples:

Rice
Oil
Salt
Potato
Onion
Soap
Shampoo
Toothpaste

Inventory fields:

- Item name
- Category
- Unit
- Current quantity
- Minimum quantity
- Brand
- Last purchase price
- Last purchase date
- Notes

When an advanced shopping item is purchased, optionally allow:

"Add to Inventory"

If enabled:

increase inventory quantity.

Example:

Existing Rice = 5 kg

Purchase = 3 kg

New inventory = 8 kg

Do not make inventory mandatory for every purchase.

---

17. Inventory Alerts

If:

Current quantity <= Minimum quantity

show:

"Low Stock"

Example:

Rice
Current: 1 kg
Minimum: 2 kg

Status:

LOW STOCK

Allow filtering:

- All
- In Stock
- Low Stock
- Out of Stock

---

18. Reports

Create a Reports section.

Show:

Daily

- Total income
- Total expense
- Shopping expense
- Transport expense
- Other expense
- Closing cash

Monthly

- Total income
- Total expense
- Shopping
- Transport
- Household
- Food
- Medicine
- Other

Shopping

- Number of shopping sessions
- Total shopping amount
- Average shopping amount
- Most purchased items

Cash

- Opening cash
- Cash added
- Expenses
- Expected closing cash
- Physical closing cash
- Difference

Use simple charts if possible.

Charts must work offline.

If a third-party chart library is used, provide a graceful fallback when unavailable.

---

19. Transactions

Create a complete transaction list.

Every transaction should have:

- ID
- Type
- Amount
- Category
- Date
- Time
- Session ID if applicable
- Description
- Created timestamp
- Updated timestamp

Types:

- Income
- Expense
- Shopping
- Transport
- Cash Snapshot
- Cash Adjustment

Allow:

- Search
- Filter
- Sort
- Edit
- Delete

Deleting important financial records should require confirmation.

---

20. Session Structure

A shopping session should be able to contain:

Session
├── Cash Start
├── Shops
│    ├── Items
│    ├── Bill
│    ├── Payment
│    └── Change
├── Journeys
│    ├── Transport
│    ├── From
│    ├── To
│    └── Cost
├── Other Expenses
└── Cash End

Do NOT create unnecessary complex architecture.

Keep the data model clean and extensible.

---

21. Multiple Device Data

This is very important.

The application must support:

Export

Export ALL application data into a portable JSON file.

Also provide:

- Export JSON
- Export Excel/CSV

Excel export should include separate sheets where practical:

- Cash Snapshots
- Denominations
- Shopping Sessions
- Shops
- Shopping Items
- Journeys
- Expenses
- Income
- Inventory
- Categories
- Transactions

If XLSX generation requires a library, use SheetJS when available.

The core application must still function offline without XLSX generation.

---

22. Import

Allow importing previously exported JSON.

Support:

Replace

Replace local data with imported data.

Merge

Merge imported data with existing local data.

Default should be:

MERGE

Do NOT blindly overwrite existing records.

---

23. Multi-device Merge

Design JSON records with stable unique IDs.

Use UUID-style IDs.

Every record should include:

- id
- createdAt
- updatedAt
- deviceId

When merging:

1. Match records by ID.
2. If ID does not exist locally → import.
3. If ID exists:
   - compare updatedAt
   - keep newest version
4. Avoid duplicate records.

Provide a simple merge summary:

Imported:
25

New:
18

Updated:
5

Skipped:
2

Conflicts:
0

The user should be able to export from Device A and import/merge into Device B.

This is a prototype, so true automatic cloud synchronization is NOT required.

---

24. Backup

Create:

Backup Now

Generate a complete JSON backup.

Also show:

Last backup date.

Add:

Restore Backup

with confirmation.

---

25. Offline-first Requirements

The app must:

- Work offline
- Persist data after browser/app restart
- Use IndexedDB
- Register a Service Worker
- Cache application assets
- Provide a basic PWA manifest
- Be installable where browser/PWA support exists

Do not depend on an online API.

If external libraries are used, structure the app so the main application remains usable offline.

---

26. Mobile UX

This is primarily a mobile application.

Optimize for:

- Android phone
- iPhone
- iPad
- small screens

Use:

- bottom navigation
- large touch targets
- floating Add button where appropriate
- compact cards
- sticky totals
- bottom sheets/modals where useful

Avoid desktop-only tables on mobile.

For denomination entry, use a clean numeric input interface.

---

27. Fast Entry

The application should be optimized for real-life speed.

A person returning from the market should be able to record:

"Rice 1090
Potato 600
Rickshaw 40"

very quickly.

Do not force the user through 20 fields.

Advanced information should always remain optional.

Design philosophy:

Simple by default.

Advanced when needed.

---

28. Daily Workflow

The application should naturally support this workflow:

Morning:

1. Count physical cash.
2. Enter denomination quantities.
3. System calculates total cash.
4. Start day/cash snapshot.

Going outside:

5. Create "First Bazar Today".
6. Enter cash taken.
7. Buy multiple items.
8. Add transport expenses.
9. Optionally enter shop details.
10. End session.
11. Enter cash returned.
12. System calculates expected vs actual cash.

Evening:

13. Review expenses.
14. Review physical cash.
15. Check inventory.
16. Export backup if desired.

---

29. Data Model

Use clean JavaScript objects.

Suggested structure:

{
  settings: {},
  categories: [],
  cashSnapshots: [],
  denominations: [],
  sessions: [],
  shops: [],
  shoppingItems: [],
  journeys: [],
  expenses: [],
  incomes: [],
  inventory: [],
  transactions: [],
  metadata: {}
}

Use IndexedDB stores instead of storing everything in localStorage.

Keep the data model versioned:

schemaVersion: 1

Prepare a migration mechanism for future schema versions.

---

30. UI Sections

Create these primary screens:

1. Dashboard
2. Cash
3. Shopping
4. Expenses
5. Inventory
6. Reports
7. Transactions
8. Settings

Settings should contain:

- Language
- Currency
- Categories
- Export
- Import
- Merge
- Backup
- Restore
- Data reset
- About

---

31. Language

Initially support:

- English
- বাংলা

Create a simple translation dictionary.

Do NOT duplicate the entire application logic for Bengali.

Example:

const translations = {
  en: {},
  bn: {}
};

Allow switching language from Settings.

---

32. Currency

Default:

Bangladeshi Taka

Symbol:

৳

Do not hard-code currency calculations everywhere.

Create a currency configuration.

---

33. Important UX Rule

Do NOT overwhelm the user.

Default forms must be extremely simple.

Example shopping entry:

Item:
[ Rice ]

Price:
[ 1090 ]

[ + Add Item ]

Advanced:
[ OFF ]

Only when Advanced is ON should additional fields appear.

Same philosophy for:

- Notes
- Shops
- Journeys
- Expenses
- Inventory

---

34. Validation

Prevent invalid data:

- Negative quantity
- Negative price
- Invalid denomination
- Empty required names
- Invalid dates
- Invalid numbers

Allow ৳0 for legitimate cases such as walking.

---

35. Financial Calculation Rules

Never calculate money using careless floating-point arithmetic.

For Bangladeshi Taka, store monetary values as integer paisa where practical, or integer taka if decimal money is intentionally not supported.

For this prototype, integer Taka is acceptable because normal household cash entries are primarily whole Taka.

All totals must be calculated programmatically.

Never allow manually entered totals to override calculated totals.

---

36. Demo Data

Include a "Load Demo Data" option.

Create realistic Bangladesh household demo data:

Cash:

৳1000 × 2
৳500 × 2
৳100 × 5
৳50 × 2
৳20 × 3
৳10 × 2
৳5 × 2
৳2 × 2

Coins:

৳5 × 3
৳2 × 4
৳1 × 5

Create sample shopping:

First Bazar Today

Rice
Potato
Oil
Vegetables

Transport:

Rickshaw

Create sample inventory.

The demo data should make it immediately obvious how the system works.

---

37. UI Quality

Make the UI polished enough to feel like a real mobile product.

Requirements:

- responsive
- clean typography
- clear hierarchy
- accessible contrast
- touch-friendly
- no unnecessary animations
- fast
- no giant empty spaces
- no unnecessary enterprise-style complexity

Use CSS variables and reusable components/classes.

---

38. Safety Against Data Loss

Before destructive actions:

- Delete all data
- Replace import
- Reset application

show confirmation.

For imports, validate the JSON structure before writing to IndexedDB.

Never crash because of malformed imported data.

---

39. Deliverables

Create:

index.html
manifest.json
service-worker.js

If absolutely necessary, additional local JS/CSS files may be created, but prefer a single HTML prototype.

The app must run simply by opening the HTML file where browser security allows it, while PWA/service-worker functionality should work when served from localhost or GitHub Pages.

---

40. Final Requirement

After implementing the prototype:

1. Test every major workflow.
2. Test page refresh.
3. Test browser restart persistence.
4. Test adding cash.
5. Test denomination calculation.
6. Test shopping session.
7. Test multiple shopping items.
8. Test transport.
9. Test session reconciliation.
10. Test inventory update.
11. Test reports.
12. Test JSON export.
13. Test JSON import.
14. Test merge.
15. Test duplicate prevention.
16. Test Excel/CSV export.
17. Test mobile layout.
18. Test Bengali/English switching.

Fix obvious bugs before finishing.

At the end, provide:

- list of created files
- short feature summary
- how to run
- known limitations
- recommended next features

Do NOT add unnecessary backend infrastructure.

The guiding principle is:

“Count the cash → go outside → buy things → record quickly → come home → reconcile cash → know exactly where the money went.”