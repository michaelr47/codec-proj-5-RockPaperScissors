# codec-proj-5-RockPaperScissors
/* Our code will break the game into four parts:
-Get the user’s choice.
-Get the computer’s choice.
-Compare the two choices and determine a winner.
-Start the program and display the results. */


const getUserChoice = (userInput) => {
userInput = userInput.toLowerCase();

if (userInput === 'rock' || userInput === 'paper' || userInput === 'scissors') {
 return userInput; 
 } else {
console.log('Message error. Please type: rock, paper, scissors');
 }
}
const getComputerChoice = () => { 
const randomNumber = Math.floor(Math.random() * 3);
 switch (randomNumber) {
   case 0: 
    return 'rock';
   case 1: 
    return 'paper';
   case 2: 
    return 'scissors';
 }
};


const determineWinner = (userChoice, computerChoice) => { 
  if (userChoice === computerChoice) {
    return 'This game is a tie!';
  }
if (userChoice === 'rock') {
  if (computerChoice === 'paper') {
  return 'The computer won!';
} else {
  return 'You won!';
 }
}
if (userChoice === 'paper') {
  if (computerChoice === 'scissors') {
    return 'Sorry, computer has beaten you!';
  } else {
  return 'Hey, you won!';
}
}
if (userChoice === 'scissors') {
  if (computerChoice === 'rock') {
    return 'Sorry, computer won!';
  } else {
    return ' Nice, you won!';
   }
  }
 };

const playGame = () => {
  const userChoice = getUserChoice('paper');
 const computerChoice = getComputerChoice();
 console.log(`You threw: ${userChoice}`);
 console.log(`Computer threw: ${computerChoice}`);

 console.log(determineWinner(userChoice, computerChoice));
};
playGame();
