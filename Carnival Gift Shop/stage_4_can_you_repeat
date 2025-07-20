const input = require("sync-input");

function displayGreeting() {
    console.log('WELCOME TO THE CARNIVAL GIFT SHOP!');
    console.log('Hello friend! Thank you for visiting the carnival!');
}

const gifts = [
    {id: 1, name: "Teddy Bear", cost: 10},
    {id: 2, name: "Big Red Ball", cost: 5},
    {id: 3, name: "Huge Bear", cost: 50},
    {id: 4, name: "Candy", cost: 8},
    {id: 5, name: "Stuffed Tiger", cost: 15},
    {id: 6, name: "Stuffed Dragon", cost: 30},
    {id: 7, name: "Skateboard", cost: 100},
    {id: 8, name: "Toy Car", cost: 25},
    {id: 9, name: "Basketball", cost: 20},
    {id: 10, name: "Scary Mask", cost: 75}
];

let tickets = 0;

function listGifts() {
    console.log("Here's the list of gifts:\n");
    gifts.forEach((gift) => {
        console.log(`${gift.id}- ${gift.name}, Cost: ${gift.cost} tickets`);
    });
}

function buyGifts() {
    const gift_id_input_msg = "Enter the number of the gift you want to get: "
    const index = Number(input(gift_id_input_msg));
    let gift = gifts.find(gift => gift.id === index);
    if (gift) {
        const {name, cost} = gift;
        console.log(`Here you go, one ${name}!`);
        let amount = -1 * cost;
        addTicket(amount);
        removeGiftById(index);
    }
}

function removeGiftById(id) {
    const index = gifts.findIndex(gift => gift.id === id);
    if (index !== -1) {
        gifts.splice(index, 1);
    }
}

function checkTickets() {
    console.log('Total tickets: ' + tickets);
}

function addTicket(amount) {
    tickets += amount;
}

function userChoice() {
    const do_what_input_msg = "\nWhat do you want to do?\n1-Buy a gift 2-Add tickets 3-Check tickets 4-Show gifts 5-Exit the shop\n"
    return input(do_what_input_msg);
}

// Start of the program
displayGreeting();
listGifts();
let key = true
do {
    let choice = userChoice();
    switch (choice) {
        case '1':
            buyGifts();
            checkTickets();
            break;
        case '2':
            const ticket_amount_input_msg = "Enter the ticket amount: "
            let amount = Number(input(ticket_amount_input_msg));
            addTicket(amount);
            checkTickets();
            break;
        case '3':
            checkTickets();
            break;
        case '4':
            listGifts();
            break;
        case '5':
            key = false;
    }
    // choice = userChoice();
} while (key);
console.log('Have a nice day!');