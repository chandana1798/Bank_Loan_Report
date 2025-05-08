--Finance Domain Project



## 1.Total Loan Applications  
**Query**  
  
select count(id) as Total_Applications from bank_loan_data  
![Image](https://github.com/user-attachments/assets/c0b87e0b-9f90-4621-b248-49afa035e8c2)


--2.PMTD Loan Applications  
**Query**  
  
select count(id) as PMTD_Total_Applications from bank_loan_data
WHERE MONTH(issue_date)=11 and Year(issue_date)=2021
![Image](https://github.com/user-attachments/assets/daa81fd4-5279-4473-a790-39b42df70362)

--3.Total Funded Amount  
**Query**  
  
SELECT SUM(loan_amount) AS Total_Funded_Amount FROM bank_loan_data
![Image](https://github.com/user-attachments/assets/f5c0e47f-7c2d-4021-93ac-78679422aecc)

--4.MTD Total Funded Amount    
**Query**  
  
SELECT SUM(loan_amount) AS MTD_Total_Funded_Amount FROM bank_loan_data
WHERE MONTH(issue_date) = 12 and Year(issue_date)=2021
![Image](https://github.com/user-attachments/assets/541fd884-71c5-4ab7-8ee4-0df3ca90434e)


--5.PMTD Total Funded Amount  
**Query**  
  
SELECT SUM(loan_amount) AS MTD_Total_Funded_Amount FROM bank_loan_data
WHERE MONTH(issue_date) = 11 and Year(issue_date)=2021
![Image](https://github.com/user-attachments/assets/0a80ee2d-a042-4550-b2b6-a15452094bce)

--6.Total Amount Received  
**Query**  
  
SELECT SUM(total_payment) AS Total_Amount_Collected FROM bank_loan_data
![Image](https://github.com/user-attachments/assets/39c84871-4eb3-4e4d-9be9-cea93852d4ce)


--7.MTD Total Amount Received  
**Query**  
  
SELECT SUM(total_payment) AS MTD_Total_Amount_Collected FROM bank_loan_data
WHERE MONTH(issue_date) = 12 and Year(issue_date)=2021
![Image](https://github.com/user-attachments/assets/e1ee0e29-59e8-4495-8d86-0427ce6af0e4)


--8.PMTD Total Amount Received  
**Query**  
  
SELECT SUM(total_payment) AS PMTD_Total_Amount_Collected FROM bank_loan_data
WHERE MONTH(issue_date) = 11 and Year(issue_date)=2021
![Image](https://github.com/user-attachments/assets/0e6fc805-a0e1-41c9-838c-4465521233cc)


--9.Average Interest Rate  
**Query**  
  
SELECT AVG(int_rate)*100 AS Avg_Int_Rate FROM bank_loan_data
![Image](https://github.com/user-attachments/assets/ea74dfc2-6fce-417f-9d25-b3636b41f58e)


--10.MTD Average Interest Rate  
**Query**  
  
SELECT AVG(int_rate)*100 AS MTD_Avg_Int_Rate FROM bank_loan_data
WHERE MONTH(issue_date) = 12 and Year(issue_date)=2021
![Image](https://github.com/user-attachments/assets/23b27c7d-ffc0-4717-bf31-556094dd36cd)


--11.PMTD Average Interest  
**Query**  
  
SELECT AVG(int_rate)*100 AS PMTD_Avg_Int_Rate FROM bank_loan_data
WHERE MONTH(issue_date) = 11 and Year(issue_date)=2021
![Image](https://github.com/user-attachments/assets/97f287de-2533-4dc8-83b3-32e74a2fb760)

--12.Avg DTI  
**Query**  
  
SELECT AVG(dti)*100 AS Avg_DTI FROM bank_loan_data
![Image](https://github.com/user-attachments/assets/91490035-831f-4de7-b268-73860e986f84)

--13.MTD Avg DTI  
**Query**  
  
SELECT AVG(dti)*100 AS MTD_Avg_DTI FROM bank_loan_data
WHERE MONTH(issue_date) = 12
![Image](https://github.com/user-attachments/assets/5d1aa824-f331-485a-986d-67c87c4b1cdb)
  
--14.PMTD Avg DTI  
**Query**  
  
SELECT AVG(dti)*100 AS PMTD_Avg_DTI FROM bank_loan_data
WHERE MONTH(issue_date) = 11
![Image](https://github.com/user-attachments/assets/b931c245-55c8-4c34-a651-669db0f73840)

--15.Good Loan Percentage  
**Query**  
  
SELECT
    (COUNT(CASE WHEN loan_status = 'Fully Paid' OR loan_status = 'Current' THEN id END) * 100.0) / 
	COUNT(id) AS Good_Loan_Percentage
FROM bank_loan_data
![Image](https://github.com/user-attachments/assets/b6d3356f-bcb0-479a-9e63-be7dadb83dd2)

--16.Good Loan Applications 
**Query**  
  
SELECT COUNT(id) AS Good_Loan_Applications FROM bank_loan_data
WHERE loan_status = 'Fully Paid' OR loan_status = 'Current'
![Image](https://github.com/user-attachments/assets/be14b7ea-61fa-4875-9247-aae8d005bf88)

--17.Good Loan Funded Amount  
**Query**  
  
SELECT SUM(loan_amount) AS Good_Loan_Funded_amount FROM bank_loan_data
WHERE loan_status = 'Fully Paid' OR loan_status = 'Current'
![Image](https://github.com/user-attachments/assets/90477ce8-b309-4992-a275-249d07ae1f45)

--18.Good Loan Amount Received
SELECT SUM(total_payment) AS Good_Loan_amount_received FROM bank_loan_data
WHERE loan_status = 'Fully Paid' OR loan_status = 'Current'
![Image](https://github.com/user-attachments/assets/55fd80d1-1733-4806-8a59-7e6f9c7f6249)


--19.Bad Loan Percentage
SELECT
    (COUNT(CASE WHEN loan_status = 'Charged Off' THEN id END) * 100.0) / 
	COUNT(id) AS Bad_Loan_Percentage
FROM bank_loan_data
![Image](https://github.com/user-attachments/assets/5ce250ef-60e0-424f-bdc9-0572f6735cec)

--20.Bad Loan Applications
SELECT COUNT(id) AS Bad_Loan_Applications FROM bank_loan_data
WHERE loan_status = 'Charged Off'
![Image](https://github.com/user-attachments/assets/32203575-0f1c-42c0-b10f-d18b06d47bff)

--21.Bad Loan Funded Amount
SELECT SUM(loan_amount) AS Bad_Loan_Funded_amount FROM bank_loan_data
WHERE loan_status = 'Charged Off'

--22.Bad Loan Amount Received
SELECT SUM(total_payment) AS Bad_Loan_amount_received FROM bank_loan_data
WHERE loan_status = 'Charged Off'

--23.Loan Status
--(a)
SELECT
        loan_status,
        COUNT(id) AS LoanCount,
        SUM(total_payment) AS Total_Amount_Received,
        SUM(loan_amount) AS Total_Funded_Amount,
        AVG(int_rate * 100) AS Interest_Rate,
        AVG(dti * 100) AS DTI
    FROM
        bank_loan_data
    GROUP BY
        loan_status

--(b)
SELECT 
	loan_status, 
	SUM(total_payment) AS MTD_Total_Amount_Received, 
	SUM(loan_amount) AS MTD_Total_Funded_Amount 
FROM bank_loan_data
WHERE MONTH(issue_date) = 12 
GROUP BY loan_status

--24.Month
SELECT 
	MONTH(issue_date) AS Month_Munber, 
	DATENAME(MONTH, issue_date) AS Month_name, 
	COUNT(id) AS Total_Loan_Applications,
	SUM(loan_amount) AS Total_Funded_Amount,
	SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY MONTH(issue_date), DATENAME(MONTH, issue_date)
ORDER BY MONTH(issue_date)

--25.State
SELECT 
	address_state AS State, 
	COUNT(id) AS Total_Loan_Applications,
	SUM(loan_amount) AS Total_Funded_Amount,
	SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY address_state
ORDER BY address_state

--26.Term
SELECT 
	term AS Term, 
	COUNT(id) AS Total_Loan_Applications,
	SUM(loan_amount) AS Total_Funded_Amount,
	SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY term
ORDER BY term

--27.Employee Length
SELECT 
	emp_length AS Employee_Length, 
	COUNT(id) AS Total_Loan_Applications,
	SUM(loan_amount) AS Total_Funded_Amount,
	SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY emp_length
ORDER BY emp_length

--28.Home ownership
SELECT 
	home_ownership AS Home_Ownership, 
	COUNT(id) AS Total_Loan_Applications,
	SUM(loan_amount) AS Total_Funded_Amount,
	SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY home_ownership
ORDER BY home_ownership

--29.Purpose
SELECT 
	purpose AS PURPOSE, 
	COUNT(id) AS Total_Loan_Applications,
	SUM(loan_amount) AS Total_Funded_Amount,
	SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY purpose
ORDER BY purpose













