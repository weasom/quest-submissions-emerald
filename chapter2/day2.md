# Quests

1. Explain why we wouldn't call `changeGreeting` in a script.
    
    Because this is a function that manipulates data using the contract and a script only reads the data already stored in the account. In order to use changeGreeting one would need to leverage a transaction.
    
2. What does the `AuthAccount` mean in the `prepare` phase of the transaction?
    
    Allows for access to the account once the owner signs the transaction. 

3. What is the difference between the `prepare` phase and the `execute` phase in the transaction?
    
    The prepare phase accesses the data in the account and passes it to the rest of the transaction. The execute phase interacts with the smart contract to perform the transaction, for instance updating a variable value.

4. This is the hardest quest so far, so if it takes you some time, do not worry! I can help you in the Discord if you have questions.

    Contract Code:
        
        pub contract HelloWorld {

        pub var greeting: String
        pub var myNumber: Int

        pub fun changeGreeting(newGreeting: String) {
            self.greeting = newGreeting
        }

        pub fun updateMyNumber(newNumber: Int) {
            self.myNumber = newNumber
        }

        init() {
            self.greeting = "Hello, World!"
            self.myNumber = 0
        }
       }
  
  Transaction Code:
  
    import HelloWorld from 0x01

    transaction(myNewNumber: Int) {

      prepare(signer: AuthAccount) {}

      execute {
        HelloWorld.updateMyNumber(newNumber: myNewNumber)
        }
    }
    
  Script Code:
  
      import HelloWorld from 0x01
      pub fun main(): Int {
        return HelloWorld.myNumber
      }
      
  Screenshot:
  
  ![image](https://user-images.githubusercontent.com/9120227/167329678-c8ee9894-3dcf-4907-9738-df8b3cad3ad9.png)

  ![image](https://user-images.githubusercontent.com/9120227/167329740-2c173594-898b-4507-9eed-eaed452f2fe1.png)
