
Virtual Assistant Behavior Tree using py_trees

This project simulates an autonomous virtual assistant using a Behavior Tree (BT) to decide how to handle meeting scheduling requests. It’s implemented in Python using the `py_trees` library.


Objective

- Model decision-making in an intelligent agent.
- Use BTs to handle conditions like calendar availability and rescheduling.
- Demonstrate hierarchical control flow using `py_trees`.



Tools Used

- Python 3.x
- [py_trees](https://py-trees.readthedocs.io/en/devel/) (for BT implementation)


Behavior Tree Structure

Tree Overview


Root (Selector)
├── Try Scheduling (Sequence)
│   ├── Is Calendar Free? (Condition)
│   └── Schedule Meeting (Action)
├── Try Rescheduling (Sequence)
│   ├── Is Reschedule Allowed? (Condition)
│   └── Suggest Reschedule (Action)
└── Decline Request (Action)


Logic Flow

1. If the calendar is free → schedule the meeting.
2. If not free but rescheduling is allowed → suggest rescheduling.
3. Otherwise → decline the meeting request.


How to Run the Script

Step 1: Install py_trees

bash
pip install py_trees


Step 2: Run the Python Script

bash
python virtual_assistant_bt_final.py


Default Test Cases

When you run the script, you will see output like:

Test Case: Calendar Free
Meeting scheduled successfully.

Test Case: Calendar Busy but Reschedule Allowed
Suggesting reschedule to user.

Test Case: Calendar Busy and Reschedule Not Allowed
Cannot schedule meeting. No options available.


Testing

You can test custom logic by changing these lines:

python
tree = py_trees.trees.BehaviourTree(root=create_tree(calendar_free=True, reschedule_allowed=True))
tree.tick()


Try changing the arguments:

- calendar_free=True/False
- reschedule_allowed=True/False

Example Custom Case

python
print("=== Custom Case ===")
tree = py_trees.trees.BehaviourTree(root=create_tree(calendar_free=True, reschedule_allowed=True))
tree.tick()

Files Included

- virtual_assistant_bt_final.py: Python script implementing the BT logic
- virtual_assistant_bt.ipynb: Jupyter Notebook version
- README.md: This file
- Optional: tree_diagram.png or .drawio file for diagram 


References

- [py_trees documentation](https://py-trees.readthedocs.io/en/devel/)
- [Behavior Trees in AI](https://en.wikipedia.org/wiki/Behavior_tree_(artificial_intelligence,_robotics_and_control))


