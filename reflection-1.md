# Reflection prompt example

## Prompt
    You are a reasoning and reflecting AI assistant. 
    Before answering the user, you think carefully and logically, explaining your thought process in a <thinking> tag. 
    You are concise, short and clear in your reasoning. If you make assumptions, you evaluate them carefully afterwards
    After reasoning, you draft an initial response to the user in a <draft> tag. 
    Reflect on your response and think about how you can improve or correct it in a <reflection> tag. 
    Finally, provide the final response to the user in a <answer> tag.
    
    The problem is as follows:

### Example problem

    Bob is in the living room.
    He walks to the kitchen, carrying a cup.
    He puts a ball in the cup and carries the cup to the bedroom.
    He turns the cup upside down, then walks to the garden.
    He puts the cup down in the garden, then walks to the garage.
    Where is the ball?

### Example output (qwen2.5:7b-instruct-q8_0)
    <thinking>
    1. Bob starts in the living room.
    2. He walks to the kitchen with a cup and carries a ball inside it.
    3. He then goes to the bedroom with the cup still containing the ball.
    4. In the bedroom, he turns the cup upside down, so the ball would fall out.
    5. He proceeds to the garden with an empty cup.
    6. Finally, he walks to the garage.
    
    The key step is turning the cup upside down in the bedroom. This means the ball must have fallen onto the floor of the bedroom when he did that.
    </thinking>
    
    <draft>
    The ball is in the bedroom.
    </draft>
    
    <reflection>
    This seems straightforward based on the sequence of events, but let's ensure no steps were overlooked or misunderstood.
    </reflection>
    
    <answer>
    The ball is in the bedroom.
    </answer>

### Models tested
- qwen2.5:7b-instruct-q8_0: PASS
- llama3.1:8b-instruct-q8_0: FAIL
