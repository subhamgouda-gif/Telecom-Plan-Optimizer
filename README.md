# Telecom Plan Optimizer

Compares sample data plans for each subscriber and recommends the lowest-cost plan that satisfies both the requested validity and budget.

## What it demonstrates

Variables, numbers, strings, tuples, lists of plans and subscribers, nested loops, conditions, arithmetic and comparison operators, and tuple unpacking. No imports or user-defined functions are used.

## Sample assumptions

- Each plan has a base price, validity in days, included data, and an excess-data rate per GB.
- Extra data is billed at the plan's excess rate.
- A plan is eligible only when its validity covers the requested days and its total cost stays within budget.
- Equal-cost eligible plans are resolved in favor of the longer validity.

Edit the plan and subscriber lists at the top of `main.py`.

## Algorithm

1. For each subscriber, examine every plan.
2. Calculate excess data and total cost.
3. Ignore plans that fail validity or budget requirements.
4. Keep the cheapest eligible plan, using validity as the tie-break.
5. Print the recommendation or report that no plan qualifies.

## Pseudocode

```text
FOR each subscriber
    best plan = none
    FOR each plan
        calculate excess data and total price
        IF validity and budget pass
            keep plan if cheaper, or longer if tied
    print best plan or no-match message
```

## Flowchart

```text
START -> Read subscriber -> Check each plan -> Validity and budget pass?
                                     | yes -> Compare with best plan
                                     | no  -> Skip plan
       -> More plans? --yes--> Check next plan
                    --no--> Print recommendation -> Next subscriber or END
```

## Run

```powershell
python main.py
```

## Live Streamlit deployment

https://telecom-plan-optimizer-xev5ndbkbjgxwxhfo8w6s7.streamlit.app/
