```php
<?php
require_once('vendor/autoload.php'); 

$multicoin = new Multicoin(['BTC', 'BCH']); 

// Get the current order total
$order_total = 1234; 

// Create a Multicoin transaction object
$transaction = new Multicoin\Transaction[$order_total]; 

// Add the recipient's wallet address and amount to the transaction
$transaction->setRecipient('BCH-BC-12345','1.00'); 

// Add the recipient's Bitcoin wallet address and amount to the transaction
$transaction->setRecipient('BTC-BC-54321','0.01'); 

// Set the Multicoin wallet address
$transaction->setSender('Multicoin');
// Set the transaction ID
$transaction->setTxId('12345'); 

// Send the transaction
$multicoin->sendPayment($transaction); 

// Get the transaction ID from the Multicoin API
$txid = $multicoin->getTransactionId($transaction); 

// Get the transaction details from the Multicoin API
$transaction_info = $multicoin->getTransactionInfo($txid); 

// Print the transaction details to the screen
print_r($transaction_info);
```
