# Snake Game AI 
AI driven snake game using Reinforcement Learning and Deep Q Learning.<br>

The game of Snake actually has a trivial, unbeatable solution. It can be driven by <b> Simple Non-ML Technique </b>by just traversing every block of the board, this gives the unbeateablre solution but it is very time taking and very brute force approach.<br>

But we will be using reinforcement learning techinque.
## Reinforcement Learning
The first question arises in mind that why we are using reinforcement learning instead of supervised machine learning, the answer is, in supervised ML algorithms need to be trained with an input and a “correct answer” called target.In this example, we don’t know what the best action to take at each stage of the game is, so a traditional approach would not be effective.<br>
In Reinforcement Learning, we have two main components: the <b>environment</b> (our game) and the <b>agent</b> (our Snake.. or to be correct, the Deep Neural Network that drives our Snake’s actions). Every time the agent performs an action, the environment gives a reward to the agent, which can be positive or negative depending on <i>how good the action was from that specific state.</i>
<p align="center">
<img src="https://github.com/Khushi9354/SnakeGameAI-reinforcement_Learning-/blob/11984043be25fdc352fcc30c38b6dad48e3e6f3e/images/struct.svg">
  </p>
Deep Reinforcement Learning (DRL) combines the above ideas of RL with deep neural networks. The neural network learns the “Q function”, which takes as input the current environment state and outputs a vector containing expected rewards for each possible action. The agent can then pick the action that maximizes the Q function. Based on this action, the game then updates the environment to a new state and assigns a reward (e.g. +10 for eating an apple, -10 for hitting a wall). At the beginning of training, the Q function is just approximated by a randomly initialized neural network. 

I will explain the implementation of this SnakeAI step by step.<br>
A simple snake board game which is user controlled is designed using pygame module is here 
https://github.com/Khushi9354/SnakeGameAI-reinforcement_Learning-/blob/abc9529837e73fd489764e889cc932f8104012db/snake_game.py
### Algorithm
We have snake and food on the board randomly placed.
* calculate the state of the snake using the 11 values 
  <img src="https://github.com/Khushi9354/SnakeGameAI-reinforcement_Learning-/blob/be65aa67bc3b5e85e6941002f526176a5e8c7ac4/images/state.svg">
* Now this current state is passed to the RL Model for the next state.
  <img src="https://github.com/Khushi9354/SnakeGameAI-reinforcement_Learning-/blob/76a1fef0e6f11d086efce2042160ef556d23d4e2/images/model.svg">
* After executing the next state calculate the reward. Rewards are defined as below:
  1. Eat food  :  +10
  2. Game Over :  -10
  3. Else      :    0
* Update the Q value and Train the Model.

After analysing the algorithm now we have to build the idea to proceed for coding this algorithm.<br><br>
Our Project will be divided into three Modules named <b>Agent, Game and Model</b>
  <p align='center'>
    <img src="https://github.com/Khushi9354/SnakeGameAI-reinforcement_Learning-/blob/b0ea04cbe3cd3353ebbc83aa2ab9dfac4c6246a5/images/Agentstate.PNG">
  </p>
  <p>
    <img src="https://github.com/Khushi9354/SnakeGameAI-reinforcement_Learning-/blob/b0ea04cbe3cd3353ebbc83aa2ab9dfac4c6246a5/images/Game.png">
    <img src="https://github.com/Khushi9354/SnakeGameAI-reinforcement_Learning-/blob/f1218a58591dfe1768df76c5743dbeb4c0734bde/images/model.png">
  </p>

<br><br><br><br><br><br><br><br><br><br><br><br>
<hr />
<p>
  <h2>Result</h2>
<img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/new.gif" width=380px height=250px align='left'>
<img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/Animation.gif" width=380px height=250px align='right'>
<br><br><br><br><br><br><br><br><br><br><br>
<p style="font-size:25px">
<pre>              <b> Initial Epochs</b>                                           <b>After 100<sup>th</sup> Epochs</b></pre>
</p>
