# Tree-of-Thought prompt example 


## Prompt

    Imagine three different problem solving experts are solving a problem.
    
    The experts thinks carefully and logically, explaining their thought process to each other.
    They are concise, short and clear in their reasoning.
    
    The process of reasoning is as follows:
    1. All experts will write down one step of their thinking
    2. All experts share their thought with the group.
    3. If any expert realises they're wrong at any point, they leave the conversation.
    
    The experts will repeat step 1-3 until the final answer is reached.
    
    Example response:
    ```markdown
    # Round 1
    - Expert 1: There is evidence that ..
    - Expert 2: I suspect that ..
    - Expert 3: The thing is ..
    
    # Round 2
    -  ...
    
    
     ...
     Final Answer: (The final answer)
    ```
    
    The problem is as follows:


## Example Problem

    Bob is in the living room.
    He walks to the kitchen, carrying a cup.
    He puts a ball in the cup and carries the cup to the bedroom.
    He turns the cup upside down, then walks to the garden.
    He puts the cup down in the garden, then walks to the garage.
    Where is the ball?

### Models tested
- llama3.1:8b-instruct-q8_0 - PASS
- qwen2.5:7b-instruct-q8_0 - PASS
- qwen2.5:3b-instruct-q8_0 - FAIL

### Example output (qwen2.5:7b-instruct-q8_0)

    ```markdown
    # Round 1
    - Expert 1: Bob walked from the living room to the kitchen with a cup.
    - Expert 2: He put a ball in the cup and carried it to the bedroom.
    - Expert 3: There, he turned the cup upside down.
    
    # Round 2
    - Expert 1: If the cup was turned upside down in the bedroom, the ball would fall out.
    - Expert 2: The ball must be on the floor of the bedroom since the cup was inverted there.
    - Expert 3: Bob then took the now empty cup to the garden and garage.
    
    # Round 3
    - Final Answer: The ball is in the bedroom.
    ```
