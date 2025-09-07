### Task 2: Dmoney API
#### Scenario Overview:
This test simulates various financial transactions in the **Dmoney API** using JMeter to evaluate performance under concurrent load.

#### API Documentation
- User [(http://dmoney.roadtocareer.net/api-docs/user/)]
- Transactions [http://dmoney.roadtocareer.net/api-docs/transaction/]
#### Test Scenario:
- **5 agents** perform **deposits** for **10 customers**.  
- **5 customers** send money to **another 10 customers**.  
- **5 customers** make **payments** to **2 merchants**.  

#### Implementation Steps:
1. **Authentication**  
   - Log in as an **admin** and generate a token.  
   - Use this token across all threads for secure transactions.  

2. **Test Configuration**  
   - Create **3 Thread Groups**:
     - **Agent Transactions (Deposit)**  
     - **Customer Transactions (Send Money)**  
     - **Merchant Transactions (Payment)**  
   - Use **CSV Data Set Config** for dynamic user data:
     - `deposit.csv` → Agent & Customer account details  
     - `sendMoney.csv` → Sender & Receiver customer details  
     - `payment.csv` → Customer & Merchant details  

3. **Dynamic Transaction Amount**  
   - Implement **Random Variable Controller** to assign random small amounts to prevent zero balance issues.  

4. **Performance Settings**  
   - Each thread has a **ramp-up time of 120 seconds** to simulate real-world usage.  

5. **Assertions for Validation**  
   - Ensure that **all transactions are successful** using assertions.  

#### Functional Test Results
- **Request Summary**
  ![image](https://github.com/user-attachments/assets/95b00971-9dad-4906-8465-0b599633ed8f)


## Notes
- The `dmoney.jtl` file and the `Report/` folder are **excluded from Git** to keep the repository clean.
- The **Excel file contains the detailed steps** for both Load & Stress tests of the **Restful Booker API**.

## Conclusion
This project ensures:
- Performance validation of the **Restful Booker API** under realistic load.
- Successful functional validation of the **Dmoney API**.

For any issues or improvements, feel free to open an **Issue** or **Pull Request**.
