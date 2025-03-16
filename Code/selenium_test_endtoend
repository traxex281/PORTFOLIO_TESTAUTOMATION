package com.serviceNow.testcases;

import java.awt.Robot;
import java.awt.Toolkit;
import java.awt.datatransfer.StringSelection;
import java.awt.event.KeyEvent;
import java.io.IOException;
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
import java.util.Set;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.Select;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.Test;

import com.relevantcodes.extentreports.ExtentTest;
import com.relevantcodes.extentreports.LogStatus;

import okhttp3.internal.NamedRunnable;

public class EndtoEnd_OpportunisticRequestProcess_Normal extends CommonTest {

	public EndtoEnd_OpportunisticRequestProcess_Normal() throws IOException {
		super();
		// TODO Auto-generated constructor stub
	}
	
	public ArrayList<String> fieldnames = new ArrayList<String>();
	public ArrayList<String> fieldtypes = new ArrayList<String>();
	public String requestid;
	public String responsedate; 
	public String RequestorEID;
	public String FulfillerEID;
	public String Password;
	public String AdsPassword;
	public String requestid1 = "CCCB0003807";
	public String requestid2 = "CCCB0003796";
	public String requestid3 = "CCCB0003763";
	public String testName = "Opportunity Request Process - Normal"; 
	public String currentWindow;
	
	
	
	//the user logs in as a Requestor
	@Test
	public void UserLoginAsRequestor() {
		ExtentTest logger = extent.startTest("User Login as Requestor", "User Login as Requestor");
		try {

			String RequestorEID = getInputData("GLOBAL", "RequestorEID");
			String RequestorPassword = getInputData("GLOBAL", "RequestorPassword");
			
			SSOlogin(logger, RequestorEID, RequestorPassword, getInputData("GLOBAL", "URL"));
			util.pause(logger, "10");
		}

		catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to Login as Requestor");

		}
		extent.endTest(logger);
		extent.flush();
	}
	
	@Test
	public void VerificationOfSubmitButton() {
		ExtentTest logger = extent.startTest("Verification of 'Submit' button",
				"Verification of 'Submit' button");

		try {
			//the user is in Accenture Policy 55-68 request form
			browserHelper.navigate(logger, getInputData("GLOBAL", "CATALOG_URL"));
			util.pause(logger, "20");
			
			// Click Accept Privacy Statement
			util.pause(logger, "10");
			
			util.clickOn(logger, portal.button(driver, "Close"));
			logger.log(LogStatus.PASS, "Privacy Statement Accepted");
			

			// Verify Awareness time-out message
			util.verifyElementByXpath(logger, portal.label(driver, "Being inactive for a period of time can cause session time-out. Please save your work from time to time"));
			logger.log(LogStatus.PASS, "Awareness time-out message is displayed");
			
			//the user checks the "Submit" button, the "Submit" button is displayed
			util.pause(logger, "5");
			util.verifyElementByXpath(logger, portal.button(driver, "Submit"));
			logger.log(LogStatus.PASS, "Submit button is displayed");
			
			//Click the Hide button in the footer - hermaine.c.t.canania[05/29/2023]
			util.pause(logger, "10");
			WebElement hidebutton = driver.findElement(By.xpath("//button[@id='dummyfooter']"));
			util.clickOn(logger, hidebutton);
			Thread.sleep(1000);
		}

		catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Submit is not displayed");
		}
		extent.endTest(logger);
		extent.flush();
	}
	
	@Test
	public void PopulateMandatoryAndNotMandatoryFields() {
		ExtentTest logger = extent.startTest("Populate mandatory and not - mandatory fields",
				"Populate mandatory and not - mandatory fields");
		
		try {
			//the user populates Opportunity details and other considerations fields
			util.scrollByVisibleElement(driver, logger, driver.findElement(By.xpath("//a[text()='Filling Instructions']")));
			portal.selectFromDroplist(logger, driver, "Type of request", getInputData(testName,"Type of request"));
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Project/Opportunity with MMS ID?"));
			portal.selectFromDroplist(logger, driver, "Project/Opportunity with MMS ID?", getInputData(testName, "Project/Opportunity with MMS ID?"));
			
			//populating fields
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Opportunity ID"));
			WebElement Opportunity_ID = driver.findElement(By.id("sp_formfield_apr_opp_details_opp_id"));
			util.setText(logger, Opportunity_ID, getInputData(testName,"Opportunity ID"));
							
			util.scrollDownByJavascriptExecutor(logger, driver);
			WebElement Opp_name = driver.findElement(By.id("sp_formfield_apr_opp_details_opp_name"));
			util.setText(logger, Opp_name, getInputData(testName,"Opportunity name"));
			WebElement Client_name = driver.findElement(By.id("sp_formfield_apr_opp_details_client_name"));
			util.setText(logger, Client_name, getInputData(testName,"Client name"));
			portal.selectFromDroplist(logger, driver, "Opportunity stage", getInputData(testName,"Opportunity stage"));
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Opportunity status"));
			portal.selectFromDroplist(logger, driver, "Opportunity status", getInputData(testName,"Opportunity status"));
			
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Client address"));
			WebElement Client_address = driver.findElement(By.id("sp_formfield_apr_opp_details_client_address"));
			util.setText(logger, Client_address, getInputData(testName,"Client address"));			
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Client type"));
			portal.selectFromDroplist(logger, driver, "Client type", getInputData(testName,"Client type"));
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Government interest"));
			portal.selectFromDroplist(logger, driver, "Government interest", getInputData(testName,"Government interest"));
			WebElement PriorMMSID = driver.findElement(By.id("sp_formfield_apr_opp_details_mms_id"));
			util.setText(logger, PriorMMSID, getInputData(testName,"Prior MMS ID & prior AP55-68 number"));		
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Brief description of the opportunity"));
			WebElement BriefDescriptionofopportunity = driver.findElement(By.id("sp_formfield_apr_opp_details_opp_desc"));
			util.setText(logger, BriefDescriptionofopportunity, getInputData(testName,"Brief description of the opportunity"));
			WebElement ContractControllableIncome = driver.findElement(By.id("sp_formfield_apr_opp_details_cci"));
			util.setText(logger, ContractControllableIncome, getInputData(testName,"Contract Controllable Income"));
			portal.selectFromDroplist(logger, driver, "Opportunity Director", getInputData(testName,"Opportunity Director"));				
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Business development agent"));
			portal.selectFromDroplist(logger, driver, "Business development agent", getInputData(testName,"Business development agent"));	
			portal.selectFromDroplist(logger, driver, "Delivery Lead", getInputData(testName,"Delivery Lead"));
			portal.selectFromDroplist(logger, driver, "Bank guarantees", getInputData(testName,"Bank guarantees"));
			portal.selectFromDroplist(logger, driver, "Client Account Lead", getInputData(testName,"Client Account Lead"));
			WebElement TimingConsiderations = driver.findElement(By.id("sp_formfield_apr_opp_details_timing_considerations"));
			util.setText(logger, TimingConsiderations, getInputData(testName,"Timing considerations"));
			
			portal.selectFromDroplist(logger, driver, "Legal or Contract Manager", getInputData(testName,"Legal or Contract Manager"));
					
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Admin charges WBS"));
			WebElement AdminchargesWBS = driver.findElement(By.id("sp_formfield_apr_opp_details_admin_charge_wbs"));
			util.setText(logger, AdminchargesWBS, getInputData(testName,"Admin charges WBS"));
			util.pause(logger, "5"); 
			
		}

		catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Fields are not populated.");
		}
		extent.endTest(logger);
		extent.flush();
	}
	
	@Test
	public void PopulateContractingInvoicingTable() {
		ExtentTest logger = extent.startTest("Populate Contracting/Invoicing Table",
				"Populate Contracting/Invoicing Table");

		try {
			
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Contracting/invoicing"));
			
			//Add row
			//util.clickByJavascriptExecutor(logger, driver, portal.btn_addcontract);
			WebElement btn_addContract = driver.findElement(By.xpath("//*[@id='3f03bd2edb0468544ef1ea7b03961986_add_row']"));
			util.clickByJavascriptExecutor(logger, driver, btn_addContract);
			util.waitTillElementIsVisible(logger, driver, portal.btn_closeModal);
			util.pause(logger, "20");
			
			//Populate Contracting/invoicing Table Modal entity
			portal.selectFromDroplist(logger, driver, "Accenture contracting country/location", getInputData(testName,"Accenture contracting country/location"));
			util.pause(logger, "3");
			portal.selectFromDroplist(logger, driver, "Accenture contracting entity", getInputData(testName,"Accenture contracting entity"));
			util.pause(logger, "3");
			
			WebElement ClientContractingEntity = driver.findElement(By.id("sp_formfield_apr_contract_client_contract_ent"));
			util.setText(logger, ClientContractingEntity, getInputData(testName,"Client contracting entity"));
			portal.selectFromDroplist(logger, driver, "Client contracting country/location", getInputData(testName,"Client contracting country/location"));	
			portal.selectFromDroplist(logger, driver, "Type of contract", getInputData(testName,"Type of contract"));
			portal.selectFromDroplist(logger, driver, "Contract market unit", getInputData(testName,"Contract market unit"));
			portal.selectFromDroplist(logger, driver, "Accenture’s assets or software license agreement?", getInputData(testName,"Accenture’s assets or software license agreement?"));
			
			if(getInputData(testName,"Accenture’s assets or software license agreement?").equals("Yes")) {
				selectOptionFromMultiSelectionUsingXpath(logger, "software license agreement, select the option that applies", "//*[@id='s2id_sp_formfield_apr_contract_licensing_agreement_choice']//input", getInputData(testName,"If Accenture's assets or software license agreement, select the option that applies:"));
			}
			
			portal.selectFromDroplist(logger, driver, "Service contracted", getInputData(testName,"Service contracted"));

			WebElement SignatureDate = driver.findElement(By.id("sp_formfield_apr_contract_signature_date"));
			util.setText(logger, SignatureDate, getInputData(testName,"Signature date"));
			WebElement ProposedEndDate = driver.findElement(By.id("sp_formfield_apr_contract_proposed_end_date"));
			util.setText(logger, ProposedEndDate, getInputData(testName,"Proposed end date"));
			WebElement ProposedStartDate = driver.findElement(By.id("sp_formfield_apr_contract_proposed_start_date"));
			util.setText(logger, ProposedStartDate, getInputData(testName,"Proposed start date"));
			
			WebElement GoverningLaw = driver.findElement(By.id("sp_formfield_apr_contract_governing_law"));
			util.setText(logger, GoverningLaw, getInputData(testName,"Governing law"));
			WebElement ContractSAPNumber = driver.findElement(By.id("sp_formfield_apr_contract_contract_no"));
			util.setText(logger, ContractSAPNumber, getInputData(testName,"Contract SAP number"));
			portal.selectFromDroplist(logger, driver, "Pricing currency", getInputData(testName,"Pricing currency"));
			WebElement ContractValueinUSD = driver.findElement(By.id("sp_formfield_apr_contract_contract_value_usd"));
			util.setText(logger, ContractValueinUSD, getInputData(testName,"Contract value in USD"));
			portal.selectFromDroplist(logger, driver, "Costs currency", getInputData(testName,"Costs currency"));		
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Invoicing currency"));
			portal.selectFromDroplist(logger, driver, "Invoicing currency", getInputData(testName,"Invoicing currency"));
			util.pause(logger, "2");
			WebElement reasons = driver.findElement(By.id("sp_formfield_apr_reason_cross_border_contract"));
			util.scrollByVisibleElement(driver, logger, reasons);
			util.setText(logger, reasons, getInputData(testName,"Reason for a cross-border contract"));
			util.pause(logger, "5");
			
			WebElement btn_Addrowcontractmodal = driver.findElement(By.xpath("/html/body/div[1]/div/div/div/div/div/div/div[3]/button[2]"));
			util.scrollByVisibleElement(driver, logger, btn_Addrowcontractmodal);
			util.clickOn(logger, btn_Addrowcontractmodal);
			util.pause(logger, "5");
			Thread.sleep(1000);
		}

		catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Contracting/Invoicing table is not populated.");
		}
		extent.endTest(logger);
		extent.flush();
	}
	
	@Test
	public void PopulateWorkLocationsTable() {
		ExtentTest logger = extent.startTest("Populate Work Locations Table",
				"Populate Work Locations Table");

		try {
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Work Locations"));
			WebElement btn_addWorkLocation = driver.findElement(By.xpath("//*[@id='d4b5dee6dbcca8544ef1ea7b039619b2_add_row']"));
			util.clickByJavascriptExecutor(logger, driver, btn_addWorkLocation);
			util.waitTillElementIsVisible(logger, driver, portal.btn_closeModal);
			util.pause(logger, "20");
			
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Contract ID"));
			
			//added codes to prevent intercept of elements
			WebDriverWait wait = new WebDriverWait(driver, 10);
			WebElement intercept = wait.until(ExpectedConditions.elementToBeClickable(By.id("s2id_sp_formfield_apr_work_location_contract_no")));
			((JavascriptExecutor) driver).executeScript("arguments[0].click();", intercept);
			util.pause(logger, "10");
			
			driver.findElement(By.id("s2id_sp_formfield_apr_work_location_contract_no")).click();
			driver.findElement(By.xpath("//div[starts-with(@id,'select2-result-label')]")).click();		
			//droplistFirstValue3("Contract ID", "");
			util.pause(logger, "5");
			
			portal.selectFromDroplist(logger, driver, "Country/location", getInputData(testName,"Country/location"));
			portal.selectFromDroplist(logger, driver, "Are you traveling by charter?", getInputData(testName,"Are you traveling by charter?"));	
			WebElement Cities = driver.findElement(By.id("sp_formfield_apr_work_location_city"));
			util.setText(logger, Cities, getInputData(testName,"Cities/region/area/GPS coordinates"));
							
			portal.selectFromDroplist(logger, driver, "Are you traveling to mines or industrial facilities?", getInputData(testName,"Are you traveling to mines or industrial facilities?"));
			portal.selectFromDroplist(logger, driver, "Potential extension of the onsite activities", getInputData(testName,"Potential extension of the onsite activities"));
			WebElement Activities = driver.findElement(By.id("sp_formfield_apr_work_location_activities_perf_onsite"));
			util.setText(logger, Activities, getInputData(testName,"Activities to perform onsite"));
			
			
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Country/location of the WBS to charge"));
			portal.selectFromDroplist(logger, driver, "Country/location of the WBS to charge", getInputData(testName,"Country/location of the WBS to charge"));
			
			
			WebElement AttributableValue = driver.findElement(By.id("sp_formfield_apr_work_location_attr_value_ctry"));
			util.setText(logger, AttributableValue, getInputData(testName,"Attributable value to this country/location"));
			
			portal.selectFromDroplist(logger, driver, "WBS level", getInputData(testName,"WBS level"));
			
			WebElement TotalNumberofResources = driver.findElement(By.id("sp_formfield_apr_work_location_total_num_of_res"));
			TotalNumberofResources.sendKeys("10");
			
			WebElement TotalDaysonSite = driver.findElement(By.id("sp_formfield_apr_work_location_total_days_onsite"));
			util.setText(logger, TotalDaysonSite, getInputData(testName,"Total number of days onsite"));
			
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Home country of the resources"));
			WebElement HomeCountry = driver.findElement(By.id("sp_formfield_apr_work_location_home_country_res"));
			HomeCountry.sendKeys("Test");
			
			WebElement TotalNumberofCompanySubcontractors = driver.findElement(By.id("sp_formfield_apr_work_location_total_num_of_sub"));
			TotalNumberofCompanySubcontractors.sendKeys("10");
			Thread.sleep(1000);
			
			//portal.btn_addrowmodal.click();
			WebElement btn_Addrowlocationmodal = driver.findElement(By.xpath("/html/body/div[1]/div/div/div/div/div/div/div[3]/button[2]"));
			util.clickByJavascriptExecutor(logger, driver, btn_Addrowlocationmodal);
			util.pause(logger, "3");
			Thread.sleep(1000);
			
			//<12.10.2021><angelika.perez><[2-013] Add a validation in Work Location > Country/Location field to avoid duplication><1279649>
			//user adds another work location item with the same Country/location
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Work Locations"));
			util.clickByJavascriptExecutor(logger, driver, btn_addWorkLocation); util.pause(logger, "30");
			util.waitTillElementIsVisible(logger, driver, portal.btn_closeModal);
			util.pause(logger, "20");
			
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Contract ID")); util.pause(logger, "5");
			driver.findElement(By.id("s2id_sp_formfield_apr_work_location_contract_no")).click();
			driver.findElement(By.xpath("//div[starts-with(@id,'select2-result-label')]")).click();	
			
			portal.mandatoryfield(driver, "Country/location").click(); portal.selectFromDroplist(logger, driver, "Country/location", getInputData(testName, "Country/location"));
			portal.mandatoryfield(driver, "Are you traveling by charter?").click();portal.selectFromDroplist(logger, driver, "Are you traveling by charter?", getInputData(testName, "Are you traveling by charter?"));	

			WebElement Cities1 = driver.findElement(By.id("sp_formfield_apr_work_location_city"));
			util.setText(logger, Cities1, getInputData(testName, "Cities/region/area/GPS coordinates"));
			portal.selectFromDroplist(logger, driver, "Are you traveling to mines or industrial facilities?", getInputData(testName,"Are you traveling to mines or industrial facilities?"));
			portal.selectFromDroplist(logger, driver, "Potential extension of the onsite activities", getInputData(testName,"Potential extension of the onsite activities"));
			WebElement Activities1 = driver.findElement(By.id("sp_formfield_apr_work_location_activities_perf_onsite"));
			util.setText(logger, Activities1, getInputData(testName,"Activities to perform onsite"));
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Country/location of the WBS to charge"));
			portal.selectFromDroplist(logger, driver, "Country/location of the WBS to charge", getInputData(testName,"Country/location of the WBS to charge"));
			WebElement AttributableValue1 = driver.findElement(By.id("sp_formfield_apr_work_location_attr_value_ctry"));
			util.setText(logger, AttributableValue1, getInputData(testName,"Attributable value to this country/location"));
			portal.selectFromDroplist(logger, driver, "WBS level", getInputData(testName,"WBS level"));
			WebElement TotalNumberofResources1 = driver.findElement(By.id("sp_formfield_apr_work_location_total_num_of_res"));
			TotalNumberofResources1.sendKeys("10");
			WebElement TotalDaysonSite1 = driver.findElement(By.id("sp_formfield_apr_work_location_total_days_onsite"));
			util.setText(logger, TotalDaysonSite1, getInputData(testName,"Total number of days onsite"));
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Home country of the resources"));
			WebElement HomeCountry1 = driver.findElement(By.id("sp_formfield_apr_work_location_home_country_res"));
			HomeCountry1.sendKeys("Test");
			WebElement TotalNumberofCompanySubcontractors1 = driver.findElement(By.id("sp_formfield_apr_work_location_total_num_of_sub"));
			TotalNumberofCompanySubcontractors1.sendKeys("10");
			util.pause(logger, "5");
			//portal.btn_addrowmodal.click();
			//portal.btn_addrowmodal.click();
			WebElement btn_Addrowlocationmodal1 = driver.findElement(By.xpath("/html/body/div[1]/div/div/div/div/div/div/div[3]/button[2]"));
			util.clickByJavascriptExecutor(logger, driver, btn_Addrowlocationmodal1);
			util.pause(logger, "3");
			Thread.sleep(1000);

			
			if(portal.label(driver, "Country/Location entered is already existing. Please enter a different Country/Location.").isDisplayed()) {
			util.verifyElementByXpath(logger, portal.label(driver, "Country/Location entered is already existing. Please enter a different Country/Location."));
			logger.log(LogStatus.PASS, "Error validation message for duplicate work location is shown");
			}
			else {util.clickByJavascriptExecutor(logger, driver, portal.button(driver, "Add"));
			util.verifyElementByXpath(logger, portal.label(driver, "Country/Location entered is already existing. Please enter a different Country/Location"));
			logger.log(LogStatus.PASS, "Error validation message for duplicate work location is shown");}
			
			//close modal
			util.clickByJavascriptExecutor(logger, driver, portal.btn_closeModal);
			util.pause(logger, "10"); 
			Thread.sleep(1000);
		}

		catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Work Locations table is not populated.");
		}
		extent.endTest(logger);
		extent.flush();
	}
	
	@Test
	public void PopulateContractorSubcontractorTable() {
		ExtentTest logger = extent.startTest("Populate Contractor Subcontractor Table",
				"Populate Contractor Subcontractor Table");

		try {
			//the user populates Opportunity details and other considerations fields
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Are there Accenture employees, Avanade employees, or 3rd party individual or independent contractors?"));
			portal.selectFromDroplist(logger, driver, "Are there Accenture employees, Avanade employees, or 3rd party individual or independent contractors?", "Yes");
			
			//the user populates Are there Accenture employees, Avanade employees, or 3rd party individual or independent contractors table
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Populate the table for Accenture/Avanade/individual contractors:"));
			WebElement btn_AccentAvanCon = driver.findElement(By.xpath("//*[@id='441fd2eedb84e8544ef1ea7b03961920_add_row']"));
			util.clickByJavascriptExecutor(logger, driver, btn_AccentAvanCon);
			util.waitTillElementIsVisible(logger, driver, portal.btn_closeModal);
			util.pause(logger, "10");
			
			driver.findElement(By.id("s2id_sp_formfield_apr_tbl_acn_emp_location")).click();
			driver.findElement(By.xpath("//div[starts-with(@id,'select2-result-label')]")).click();	
			util.pause(logger, "5");
			
			portal.selectFromDroplist(logger, driver, "Resource EID", getInputData(testName,"Resource EID"));
			
			WebElement TravelDates = driver.findElement(By.id("sp_formfield_apr_tbl_acn_emp_travel_dates_fad"));
			util.setTextWithEnter(logger, TravelDates, getInputData(testName,"List of Travel dates"));
			Thread.sleep(1000);
			TravelDates.clear();

			util.setTextWithEnter(logger, TravelDates, getInputData(testName, "List of Travel dates"));
			Thread.sleep(1000);
			TravelDates.clear();
//			populateSpecialDatepicker2(logger,"Travel dates", "2021-12-10");
			
			portal.selectFromDroplist(logger, driver, "Type of resource", getInputData(testName,"Type of resource"));
			
			WebElement OnSitePresence = driver.findElement(By.id("sp_formfield_apr_tbl_acn_emp_onsite_presence_hclm"));
			util.setText(logger, OnSitePresence, getInputData(testName,"Onsite presence in the host country/location during the last 12 months"));			
			
			WebElement btn_AddrowAccenmodal = driver.findElement(By.xpath("/html/body/div[1]/div/div/div/div/div/div/div[3]/button[2]"));
			util.clickByJavascriptExecutor(logger, driver, btn_AddrowAccenmodal);
			util.pause(logger, "3");
			Thread.sleep(1000);
			
			//the user populates company subcontractors fields
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Are there company subcontractors?"));
			portal.selectFromDroplist(logger, driver, "Are there company subcontractors?", getInputData(testName, "Are there company subcontractors?"));
			util.pause(logger, "5");
			
						
			//the user populates company subcontractors table modal
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Populate the table for company subcontractors:")); 
			WebElement btn_AccentSubCon = driver.findElement(By.xpath("//*[@id='57f4aeaadbc8e8544ef1ea7b03961919_add_row']")); 
			btn_AccentSubCon.click();
			util.waitTillElementIsVisible(logger, driver, portal.btn_closeModal); 
			util.pause(logger, "10"); 

			driver.findElement(By.id("s2id_sp_formfield_apr_tbl_subcontractor_location")).click();
			driver.findElement(By.xpath("//div[starts-with(@id,'select2-result-label')]")).click();
			
			WebElement NumberofResource = driver.findElement(By.id("sp_formfield_apr_tbl_subcontractor_no_resource")); 
			util.setText(logger, NumberofResource, getInputData(testName,"Number of resources"));
			
			WebElement LegalName = driver.findElement(By.id("sp_formfield_apr_tbl_subcontractor_legal_name_ctry")); 
			util.setText(logger, LegalName, getInputData(testName,"Legal name"));
			
			portal.selectFromDroplist(logger, driver, "Country/location of incorporation", getInputData(testName,"Country/location of incorporation")); 
					
			WebElement NumberofDaysOnsite = driver.findElement(By.id("sp_formfield_apr_tbl_subcontractor_num_days_onsite")); 
			util.setText(logger, NumberofDaysOnsite, getInputData(testName,"Number of days onsite")); 
			
			WebElement LocResource = driver.findElement(By.id("sp_formfield_apr_tbl_subcontractor_loc_resources")); 
			util.setText(logger, LocResource, getInputData(testName,"Locations of the resources")); 
			
			WebElement btn_AddrowSubmodal = driver.findElement(By.xpath("//button[@class='btn btn-primary ng-binding']")); 
			util.clickByJavascriptExecutor(logger, driver, btn_AddrowSubmodal); 
			util.pause(logger, "3"); 
			
			
			//populate Subcontractor fields 
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "BI approved?")); 
			portal.selectFromDroplist(logger, driver, "BI approved?", getInputData(testName,"BI approved?")); 
			WebElement ContractingAccenEntity = driver.findElement(By.id("sp_formfield_apr_subcontractor_contra_acn_entity")); 
			util.setText(logger, ContractingAccenEntity, getInputData(testName,"Contracting accenture entity")); 
			WebElement SubcontractingInvoicing = driver.findElement(By.id("sp_formfield_apr_subcontractor_sub_invoicing")); 
			util.setText(logger, SubcontractingInvoicing, getInputData(testName,"Subcontractor invoicing"));
			portal.selectFromDroplist(logger, driver, "Accenture contractual liability", getInputData(testName,"Accenture contractual liability"));
			
			driver.findElement(By.id("s2id_sp_formfield_apr_subcontractor_resp_sub_emp_imm_mat")).click();
			util.pause(logger, "5");
			driver.findElement(By.xpath("//li[2]//div[1]")).click();
			util.pause(logger, "2");
			driver.findElement(By.id("s2id_sp_formfield_apr_subcontractor_resp_sub_emp_safe_sec")).click();
			util.pause(logger, "5");
			driver.findElement(By.xpath("//li[2]//div[1]")).click();
			util.pause(logger, "2");
			
			//portal.selectFromDroplist(logger, driver, "Responsible of subcontractor's employees immigration matters", getInputData(testName,"Responsible of subcontractor")); 
			//portal.selectFromDroplist(logger, driver, "Responsible of the subcontractor employees' safety and security ", getInputData(testName,"Responsible of the subcontractor employees"));
			portal.selectFromDroplist(logger, driver, "Client agreement allows subcontracting?", getInputData(testName,"Client agreement allows subcontracting?"));  
			portal.selectFromDroplist(logger, driver, "Confirm agreement with subcontractor requires compliance with local legislation", getInputData(testName,"Confirm agreement with subcontractor requires compliance with local legislation")); 
			util.pause(logger, "5");
		}

		catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Contractor Subcontractor table is not populated.");
		}
		extent.endTest(logger);
		extent.flush();
	}
	
	
	//<12/23/2021> <[9-006A] Attachments in Requestor form are reflected in Fulfiller task form> <angelika.perez> <1279852>	
	@Test
	public void VerificationofAttachmentIcon() {
		ExtentTest logger = extent.startTest("Verification when attachments are added to request",
				"Verification when attachments are added to request");

		try {
			//upload file
			uploadAttachmentOnPortalPage(logger, "test_attachment_requestor.txt");
			util.pause(logger, "15");
			//verify uploaded file
			util.verifyElementByXpath(logger, portal.label(driver, "test_attachment_requestor.txt"));
		}

		catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Incorrect behavior when attaching.");
		}
		extent.endTest(logger);
		extent.flush();
	}
	
	@Test
	public void VerificationWhenSubmitIsSelected() {
		ExtentTest logger = extent.startTest("Verification when Submit button is selected",
				"Verification when Submit button is selected");

		try {
			
			//the user clicks the "Submit" button
			util.pause(logger, "5");
			util.scrollByVisibleElement(driver, logger, portal.btn_submit);
			portal.btn_submit.click();
			logger.log(LogStatus.PASS, "Submit button is clicked");
			util.waitTillElementIsVisible(logger, driver, portal.reqid); util.pause(logger, "20");
						
			//saving requestid 
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Request ID"));		
			util.pause(logger, "5");
			requestid =  util.getElementValue(logger, portal.reqid);
			System.out.println(requestid);
			util.verifyElementByXpath(logger, portal.text(driver, "Request ID"));
			logger.log(LogStatus.PASS, "Request ID field is displayed.");
			logger.log(LogStatus.PASS, "Request ID is " + requestid);
			util.pause(logger, "5");
			
			verifyTextInDroplistOnPortal2(logger, "Request status","Ready");		
			logger.log(LogStatus.PASS, "Request status field is displayed.");
			logger.log(LogStatus.PASS, "Request status is Ready.");
			util.pause(logger, "5");
		}

		catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Incorrect behavior when submitting.");
		}
		extent.endTest(logger);
		extent.flush();
	}
	
	//<11/25/2021> <Clicking Launch review/Fast track review button to perform saving function> <karen.b.nicolas> <1284806>					

	//the user logs in as a Fulfiller
		@Test
		public void UserLoginAsFulfiller() {
			ExtentTest logger = extent.startTest("User Login as Fulfiller", "User Login as Fulfiller");
			try {

				String FulfillerPassword = getInputData("GLOBAL", "FulfillerPassword");
				String FulfillerEID = getInputData("GLOBAL", "FulfillerEID");
				
				SSOlogin(logger, FulfillerEID, FulfillerPassword, getInputData("GLOBAL", "URL"));
				browserHelper.navigate(logger, getInputData("GLOBAL", "NAVPAGE_URL"));
				util.pause(logger, "10");
			}

			catch (Exception e) {
				util.screenShotAndErrorMsg(logger, e, driver, "Unable to Login as Fulfiller");

			}
			extent.endTest(logger);
			extent.flush();
		}
		
		@Test
		public void impersonateAsFulfiller() {
			ExtentTest logger = extent.startTest("Impersonate as Fulfiller", "Impersonate as Fulfiller");
			
			try {

				frameHelper.switchToDefaultFrame(logger, driver);
				impersonateAsUser(logger, "maggie.mengqi.li");
				util.pause(logger, "15");
				logger.log(LogStatus.PASS, "Impersonate as Fulfiller");

				util.scrollByVisibleElement(driver, logger, portal.tooltip(driver, "Menu"));
				util.waitTillElementIsClickable(logger, driver, portal.tooltip(driver, "Menu"));
				util.clickByJavascriptExecutor(logger, driver, portal.tooltip(driver, "Menu"));
				util.pause(logger, "5");
				
				util.scrollByVisibleElement(driver, logger, portal.link(driver, "Go to fulfill.accenture.com"));
				util.clickByJavascriptExecutor(logger, driver, portal.link(driver, "Go to fulfill.accenture.com"));
				util.pause(logger, "5");
				
				util.waitTillElementIsClickable(logger, driver, nav.backgroundText(driver, "Filter navigator",""));
				
				
			} catch (Exception e) {
				util.screenShotAndErrorMsg(logger, e, driver, "Unable to impersonate");
			}
			extent.endTest(logger);
			extent.flush();

		}
		
		@Test
		public void NavigateToAllPolicyRequestTask() {
			ExtentTest logger = extent.startTest("Navigate to All Policy 55/68 Request Task", "Navigate to All Policy 55/68 Request Task");
		
			try {				
				//search Table
				List<String> item=new ArrayList<String>();
				util.pause(logger, "10");
		           item.add("Policy 55/ Policy 68 Approval Tool");
		           item.add("Policy 55/68 Request Tasks");
		           shadowDomSearchFilter(logger,item.get(0),item,"Policy 55/ Policy 68 Approval Tool");
				
				// Click the Request task using shadow DOM - hermaine.c.t.canania
		        JavascriptExecutor jse = (JavascriptExecutor) driver;
				WebElement reqtask = (WebElement) jse.executeScript("return document.querySelector('macroponent-f51912f4c700201072b211d4d8c26010').shadowRoot.querySelector('sn-polaris-layout').shadowRoot.querySelector('sn-polaris-header').shadowRoot.querySelector('sn-polaris-menu.is-main-menu.is-pinned.can-animate').shadowRoot.querySelector('sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(9) > sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(2) > span > a')");
				((JavascriptExecutor) driver).executeScript("arguments[0].click();", reqtask);
				
			}			
			catch (Exception e) {
				util.screenShotAndErrorMsg(logger, e, driver, "All Policy 55/68 Request Tasks is not displayed");
			}
			extent.endTest(logger);
			extent.flush();
		}
		

		
		@Test
		public void VerificationOfCreatedReadyRequestFulfillerView() {
			ExtentTest logger = extent.startTest("Verification Of Created Ready Request Fulfiller View",
					"Verification Of Created Ready Request Fulfiller View");
			
			try {
				//search Table
				List<String> item=new ArrayList<String>();
				util.pause(logger, "10");
		           item.add("Policy 55/ Policy 68 Approval Tool");
		           item.add("Policy 55/68 Request Tasks");
		           shadowDomSearchFilter(logger,item.get(0),item,"Policy 55/ Policy 68 Approval Tool");
				
				// Click the Request task using shadow DOM - hermaine.c.t.canania
		        JavascriptExecutor jse = (JavascriptExecutor) driver;
				WebElement reqtask = (WebElement) jse.executeScript("return document.querySelector('macroponent-f51912f4c700201072b211d4d8c26010').shadowRoot.querySelector('sn-polaris-layout').shadowRoot.querySelector('sn-polaris-header').shadowRoot.querySelector('sn-polaris-menu.is-main-menu.is-pinned.can-animate').shadowRoot.querySelector('sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(9) > sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(2) > span > a')");
				((JavascriptExecutor) driver).executeScript("arguments[0].click();", reqtask);
				
				openRecord(logger,requestid,"Request ID");
				util.pause(logger, "10");
		
			}

			catch (Exception e) {
				util.screenShotAndErrorMsg(logger, e, driver,
						"Cancelled request in fulfiller view is incorrect.");
			}
			extent.endTest(logger);
			extent.flush();
		}
		
		//<12/23/2021> <[9-006A] Attachments in Requestor form are reflected in Fulfiller task form> <angelika.perez> <1279852>	
		@Test
		public void VerificationofAttachedFilefromRequestForminFulfiller() {
		ExtentTest logger = extent.startTest("Verification for attachments shown in fulfiller side",
				"Verification for attachments shown in fulfiller side");

		try {
			//verify attachment icon and attachment from requestor is shown in fulfiller
			WebElement managedocument = driver.findElement(By.xpath("//*[@id='header_add_attachment']"));
			util.verifyElementByXpath(logger, managedocument);
			util.verifyElementByXpath(logger, portal.label(driver, "test_attachment_requestor.txt"));
			
			//verify fulfiller can attach files
			util.pause(logger, "5");
			String filename = "test_attachment_fulfiller.txt";
			String filePath = System.getProperty("user.dir") + " " + filename;
			System.out.println("FilePath:" + filePath);
			WebElement AddAttachment= driver.findElement(By.xpath("//button[@id='header_add_attachment']"));
			util.clickOn(logger, AddAttachment); util.pause(logger, "7");
			WebElement Choosefile= driver.findElement(By.xpath("//input[@id='loadFileXml']"));
			Choosefile.click();
			Robot robot= new Robot();
			StringSelection file= new StringSelection(filePath);
			Toolkit.getDefaultToolkit().getSystemClipboard().setContents(file, null);
			robot.keyPress(KeyEvent.VK_CONTROL); Thread.sleep(1000);
			robot.keyPress(KeyEvent.VK_V); Thread.sleep(1000);
			robot.keyRelease(KeyEvent.VK_V); robot.keyRelease(KeyEvent.VK_CONTROL);
			robot.keyPress(KeyEvent.VK_ENTER); Thread.sleep(1000);
			logger.log(LogStatus.PASS, "File attached to the request"); util.pause(logger, "15");
			util.waitTillElementIsClickable(logger, driver, nav.btn_closeModal);
			util.clickOn(logger, nav.btn_closeModal); util.pause(logger, "5");
			util.verifyElementByXpath(logger, nav.label(driver, "test_attachment_fulfiller.txt",""));
			
		}

		catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Attachment not shown in fulfiller side.");
		}
		extent.endTest(logger);
		extent.flush();
	}
		
		
	@Test
		public void generateP68ReviewTask() {
			ExtentTest logger  = extent.startTest("User generates a P68 Review Task", "User generates a P68 Review Task");
			
			try {
				
				//mandatory fields
				//populate required fields
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Business pre-approval?", ""));
				util.selectBoxByValue(logger, nav.dropdown(driver, "Business pre-approval?", ""), "No");
				util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Additional actions", "", "")); util.pause(logger, "2");
				util.clickByJavascriptExecutor(logger, driver, nav.label(driver, "Save", ""));
				util.pause(logger, "15");
				
				//Generate Review Task AP68
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Contract Details", "")); 
				util.pause(logger, "3");
				
				//Added code for mouse hover to the preview button - hermaine.c.t.canania
				WebElement preview = driver.findElement(By.xpath("//*[contains(@aria-label,'Preview')]/parent::td"));
	
				//Creating object of an Actions class
				Actions action = new Actions(driver);
	
				//Performing the mouse hover action on the target element.
				action.moveToElement(preview).perform();
				
				util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Preview", "", "Contract Details"));
				util.waitTillElementIsClickable(logger, driver, nav.button(driver, "Open Record", ""));
				util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Open Record", ""));
				util.pause(logger, "5"); util.waitTillElementIsVisible(logger, driver, nav.label(driver, "Extension?", ""));
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Policy 68 XBC?", ""));
				util.selectBoxByValue(logger, nav.dropdown(driver, "Policy 68 XBC?", ""), "Yes");
				util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Update", ""));
					
				
			}
			
			catch (Exception e) {
				util.screenShotAndErrorMsg(logger, e, driver, "Policy 68XBC Review task is not generated");
			}
			
		extent.endTest(logger);
        extent.flush();
		
		}

		
		@Test
		public void generateP55ReviewTask() {
			ExtentTest logger  = extent.startTest("User generates a P55 Review Task", "User generates a P55 Review Task");
			
			try {
				
				//generate AP55 review task
				util.scrollByVisibleElement(driver, logger, nav.tab_contractdetails); nav.tab_worklocations.click();
				util.pause(logger, "3");
				
				//Added code for mouse hover to the preview button - hermaine.c.t.canania
				WebElement previewworklocation = driver.findElement(By.xpath("//*[contains(@aria-label,'Preview')]/parent::td//a[@data-list_id='x_amspi_policy_request_task.x_amspi_policy_req_work_location.task_number']"));
	
				//Performing the mouse hover action on the target element.
				Actions action = new Actions(driver);
				action.moveToElement(previewworklocation).perform();
				
				util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Preview", "", "Work Locations"));
				util.waitTillElementIsClickable(logger, driver, nav.button(driver, "Open Record", ""));
				util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Open Record", ""));
				util.pause(logger, "5"); util.waitTillElementIsVisible(logger, driver, nav.label(driver, "Country/location", ""));
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Policy 55?", ""));
				util.selectBoxByValue(logger, nav.dropdown(driver, "Policy 55?", ""), "Yes");
				util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Update", ""));
				
			}
			
			catch (Exception e) {
				util.screenShotAndErrorMsg(logger, e, driver, "Policy 55 Review task is not generated");
			}
			
		extent.endTest(logger);
        extent.flush();
		
		}
		
		@Test
		public void verifyP68ReviewTask() {
			ExtentTest logger  = extent.startTest("User verifies generated P68 Review Task", "User verifies generated P68 Review Task");
			
			try {				
				util.pause(logger, "5"); util.scrollByVisibleElement(driver, logger, nav.tab_contractdetails);
				util.clickByJavascriptExecutor(logger, driver, nav.tab_reviewtasks); util.pause(logger, "5");
				OpenP68ReviewTask(logger); util.pause(logger, "5");
								
				//<11/25/2021> <Clicking Launch review/Fast track review button to perform saving function> <karen.b.nicolas> <1284806>					
	
				//Update some fields before clicking Launch Review to verify the saving function.
				util.pause(logger, "5");
				util.selectBoxByValue(logger, nav.dropdown(driver, "Policy breach?", ""), "Yes");
				util.clickOn(logger, nav.text(driver, "Additional comments", ""));
				util.setText(logger, nav.text(driver, "Additional comments", ""), "This is only a test");

				//User Launches the Review task
				util.pause(logger, "5");
				util.verifyElementByXpath(logger, nav.label(driver, "Recoveries", ""), "Recoveries");
				util.selectBoxByValue(logger, nav.dropdown(driver, "Recoveries", ""), "To be charged");
				util.clickOn(logger, nav.button(driver, "Launch Review", ""));
				 util.pause(logger, "5");
				util.verifySelectedValueInDropdown(logger, nav.dropdown(driver, "Review status", ""),  "Work in Progress");
				util.verifySelectedValueInDropdown(logger, nav.dropdown(driver, "Policy breach?", ""), "Yes");
				util.verifyExactText(logger, nav.text(driver, "Additional comments", ""), "This is only a test");
				
				//Update some fields before clicking Fast Track Review to verify the saving function.
				util.pause(logger, "5");
				util.selectBoxByValue(logger, nav.dropdown(driver, "Policy breach?", ""), "No");
				util.clickOn(logger, nav.text(driver, "Additional comments", "")); util.clearText(logger, nav.text(driver, "Additional comments", ""));
				util.setText(logger, nav.text(driver, "Additional comments", ""), "Fast track review");
				
				//User clicks Fast Track button
				util.pause(logger, "5");
				util.clickOn(logger, nav.button(driver, "Fast Track Review", ""));
				
				util.verifySelectedValueInDropdown(logger, nav.dropdown(driver, "Policy breach?", ""), "No");
				util.verifyExactText(logger, nav.text(driver, "Additional comments", ""), "Fast track review");
			
				}
			
				catch (Exception e) {
					util.screenShotAndErrorMsg(logger, e, driver, "Policy 68XBC Review task is not clicked");
				}			
				extent.endTest(logger);
				extent.flush();	
			}
		
			
			@Test
			public void verifyP68Activitylog() {
				ExtentTest logger  = extent.startTest("User verifies P68 Activity log", "User verifies P68 Activity log");
		
					try {	
						util.pause(logger, "5");	
						//user clicks Activities tab
						util.clickByJavascriptExecutor(logger, driver, nav.tab_activities);	
						
						//<01/18/2022> <[[6-009] Notifications: From Optional to Auto-sent> <angelika.perez> <1367931>	
						//verify email notification to preparer is autosent
						util.scrollByVisibleElement(driver, logger, nav.tab_activities);
						util.clickOn(logger, nav.tab_activities); util.pause(logger, "3");
						LoadAutosentEmailNotificationinActivities(logger, "Your case is now under review: "); util.pause(logger, "10");
						util.scrollByVisibleElement(driver, logger, nav.label(driver, "Your case is now under review: ", ""));
						util.checkForContainsText(logger, nav.launchreviewrequestorrecipient, RequestorEID+"@email.com");
						//verify email notication is autosent to SME reviewers
						util.scrollByVisibleElement(driver, logger, nav.label(driver, "Action Required: Your review is requested for", ""));
						util.verifyElementByXpath(logger, nav.label(driver, "Action Required: Your review is requested for "+requestid, ""));
					}
					catch (Exception e) {
						util.screenShotAndErrorMsg(logger, e, driver, "Policy 68XBC Activity log tab is not clicked");
					}		
				extent.endTest(logger);
				extent.flush(); 
			}
			
		@Test
		public void VerifyAttachmentFunctioninCFReview() {
			ExtentTest logger  = extent.startTest("User verifies attachment functionality in CF review and Conditions related list", "User verifies attachment functionality in CF review and Conditions related list");
	
				try {
					UserLoginAsFulfiller();
					NavigateToAllPolicyRequestTask();
					
					//open request task
					openRecord(logger,requestid,"Request ID");
					util.pause(logger, "10");
					
					//open the review task
					util.pause(logger, "5"); util.scrollByVisibleElement(driver, logger, nav.tab_contractdetails);
					util.clickByJavascriptExecutor(logger, driver, nav.tab_reviewtasks); util.pause(logger, "5");
					OpenP68ReviewTask(logger); util.pause(logger, "5");

					util.scrollByVisibleElement(driver, logger, nav.tab_CFreviews);
					
					//Added code for mouse hover to the preview button - hermaine.c.t.canania
					WebElement preview = driver.findElement(By.xpath("//*[@id='x_amspi_policy_req_review_task_v2.x_amspi_policy_req_corpoorate_function_review_v2.parent_table']//tbody//tr//td[2]//a"));			
					Actions action = new Actions(driver);
					action.moveToElement(preview).perform();
					
					util.pause(logger, "5");
					util.clickOn(logger, preview);
					util.pause(logger, "5");
					util.waitTillElementIsClickable(logger, driver, nav.link(driver, "Open Record", ""));
					util.clickOn(logger, nav.link(driver, "Open Record", ""));
					util.pause(logger, "5");
					
					//verify attachment icon in CF review and attach a file
					util.pause(logger, "5");
					String filename = "test_attachment_CFreview.txt";
					String filePath = System.getProperty("user.dir") + " " + filename;
					System.out.println("FilePath:" + filePath);
					WebElement AddAttachment= driver.findElement(By.xpath("//button[@id='header_add_attachment']"));
					util.clickOn(logger, AddAttachment); util.pause(logger, "7");
					WebElement Choosefile= driver.findElement(By.xpath("//button[text()='Choose file']"));
					Choosefile.click();
					Robot robot= new Robot();
					StringSelection file= new StringSelection(filePath);
					Toolkit.getDefaultToolkit().getSystemClipboard().setContents(file, null);
					robot.keyPress(KeyEvent.VK_CONTROL); Thread.sleep(1000);
					robot.keyPress(KeyEvent.VK_V); Thread.sleep(1000);
					robot.keyRelease(KeyEvent.VK_V); robot.keyRelease(KeyEvent.VK_CONTROL);
					robot.keyPress(KeyEvent.VK_ENTER); Thread.sleep(1000);
					logger.log(LogStatus.PASS, "File attached to the request"); util.pause(logger, "15");
					util.waitTillElementIsClickable(logger, driver, nav.btn_closeModal);
					util.clickOn(logger, nav.btn_closeModal); util.pause(logger, "5");
					util.verifyElementByXpath(logger, nav.label(driver, "test_attachment_CFreview.txt", ""));
					
					//verify no attachment icon in conditions related list form
					WebElement conditions = driver.findElement(By.xpath("//span[contains(text(),'Conditions')]/parent::a"));
					util.scrollByVisibleElement(driver, logger, conditions);
					util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "New", ""));
					util.waitTillElementIsVisible(logger, driver, nav.label(driver, "Active", ""));
					util.verifyElementNotDisplayed(logger, driver.findElement(By.xpath("//button[@id='header_add_attachment']")));
					nav.checkbox(driver, "Active", "").click(); 
					nav.text(driver, "Conditions", "").click();
					util.setText(logger, nav.text(driver, "Conditions", ""), "This is only a test condition");
					util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Submit", ""));
					
					//verify no attachment icon in created condition item
					util.scrollByVisibleElement(driver, logger, driver.findElement(By.xpath("//span[contains(text(),'Conditions')]/parent::a")));
					WebElement preview1 = driver.findElement(By.xpath("//*[@id='x_amspi_policy_req_corpoorate_function_review_v2.REL:6fa4ab4d1b537410270c11b6bc4bcb75_table']//tbody//tr//td[2]//a"));
					action.moveToElement(preview1).perform();
					
					util.pause(logger, "5");
					util.clickOn(logger, preview1);
					util.pause(logger, "5");
					util.waitTillElementIsClickable(logger, driver, nav.link(driver, "Open Record", ""));
					util.clickOn(logger, nav.link(driver, "Open Record", ""));
					util.pause(logger, "5");
					 
					util.verifyElementNotDisplayed(logger, driver.findElement(By.xpath("//button[@id='header_add_attachment']")));
					
				}
				catch (Exception e) {
					util.screenShotAndErrorMsg(logger, e, driver, "Review status is not set to Approved");
				}		
			extent.endTest(logger);
			extent.flush();
		}
		
			@Test
			public void setP68ReviewStatustoApproved() {
				ExtentTest logger  = extent.startTest("User updates P68 review status to Approved", "User updates P68 review status to Approved");
		
					try {
						//back to review task
						util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Back", "", ""));
						util.waitTillElementIsVisible(logger, driver, nav.label(driver, "Corporate Function Review", ""));
						util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Back", "", "")); 
						
						util.pause(logger, "5");	
						//user clicks Review task tab
						WebElement reviewtab = driver.findElement(By.xpath("//span[contains(text(),'Review Task')]/parent::span"));
						util.clickOn(logger, reviewtab);	
						
						//user selects Approved in the Review status field
						util.selectBoxByValue(logger, nav.reviewstatus, "Approved");
						util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Additional actions", "", ""));
						util.clickByJavascriptExecutor(logger, driver, nav.label(driver, "Save", "")); 
						util.pause(logger, "10");
						
						//<01/18/2022> <[[6-009] Notifications: From Optional to Auto-sent> <angelika.perez> <1367931>
						util.clickByJavascriptExecutor(logger, driver, nav.tab_activities);
						//verify Approved email notification to Opportunity director is autosent
						util.clickByJavascriptExecutor(logger, driver, nav.tab_activities);
						LoadAutosentEmailNotificationinActivities(logger, requestid+" - "+getInputData(testName, "Accenture contracting country/location")+" has been Approved");
						util.verifyElementByXpath(logger, nav.label(driver, requestid+" - "+getInputData(testName, "Accenture contracting country/location")+" has been Approved", ""));
						
					}
					catch (Exception e) {
						util.screenShotAndErrorMsg(logger, e, driver, "Review status is not set to Approved");
					}		
				extent.endTest(logger);
				extent.flush();
			}
			
			@Test
			public void AttachmentsandConditionsExtractedinReviewStatusView() {
				ExtentTest logger  = extent.startTest("User verifies extraction of Attachments and Conditions in Review status view", "User verifies extraction of Attachments and Conditions in Review status view");
		
					try {	
						String RequestorEID = getInputData("GLOBAL", "RequestorEID");
						String RequestorPassword = getInputData("GLOBAL", "RequestorPassword");
						
						SSOlogin(logger, RequestorEID, RequestorPassword, getInputData("GLOBAL", "URL"));
						util.pause(logger, "10");
						
						//the user will check Request Status in portal
						browserHelper.navigate(logger, getInputData("GLOBAL", "QUEUE_URL"));
						 util.pause(logger, "3");
						util.waitTillElementIsVisible(logger, driver, portal.label(driver, "Request ID"));
						util.clickOn(logger, portal.label(driver, "Review Status"));
						util.pause(logger, "5");
						
						//user verifies links for Attachments and Conditions for the review
						util.scrollByVisibleElement(driver, logger, portal.label(driver, "Request ID"));
						util.setTextWithEnter(logger, driver.findElement(By.xpath("//div[2]/div/div/div[2]/table/thead/tr/th[1]/div[2]/input")), requestid); util.pause(logger, "7");
						util.setTextWithEnter(logger, driver.findElement(By.xpath("//th//div[contains(text(),'Applicable Policy')]//following::div[1]//input")), "AP68 XBC"); util.pause(logger, "7");
						util.scrollByVisibleElement(driver, logger, driver.findElement(By.xpath("//table[@id='myTable']/thead/tr/th[11]")));
						util.verifyElementByXpath(logger, portal.label(driver, "Conditions & Attachments"));
						util.verifyElementByXpath(logger, portal.link(driver, "Attachments"));
						util.verifyElementByXpath(logger, portal.link(driver, "Conditions"));
						
						//user verifies Conditions pdf is downloaded when Conditions link is clicked
						util.clickByJavascriptExecutor(logger, driver, portal.link(driver, "Conditions"));
						util.pause(logger, "5");
						isFileDownloaded("Conditions.pdf");
						
						//user verifies attachments zip file is downloaded when Attachments link is clicked
						util.clickByJavascriptExecutor(logger, driver, portal.link(driver, "Attachments"));
						isFileDownloaded("Attachments.zip");
						
					}
					catch (Exception e) {
						util.screenShotAndErrorMsg(logger, e, driver, "Extraction of Attachment and Conditions in Review status view not available");
					}		
				extent.endTest(logger);
				extent.flush();
			}
		
		@Test
			public void verifyP55ReviewTask() {
				ExtentTest logger  = extent.startTest("User verifies generated P55 Review Task", "User verifies generated P55 Review Task");
				
				try {
					String FulfillerPassword = getInputData("GLOBAL", "FulfillerPassword");
					String FulfillerEID = getInputData("GLOBAL", "FulfillerEID");
					
					SSOlogin(logger, FulfillerEID, FulfillerPassword, getInputData("GLOBAL", "URL"));
					browserHelper.navigate(logger, getInputData("GLOBAL", "NAVPAGE_URL"));
					util.pause(logger, "10");
					
					//search Table
					List<String> item=new ArrayList<String>();
					util.pause(logger, "10");
			           item.add("Policy 55/ Policy 68 Approval Tool");
			           item.add("Policy 55/68 Request Tasks");
			           shadowDomSearchFilter(logger,item.get(0),item,"Policy 55/ Policy 68 Approval Tool");
					
					// Click the Request task using shadow DOM - hermaine.c.t.canania
			        JavascriptExecutor jse = (JavascriptExecutor) driver;
					WebElement reqtask = (WebElement) jse.executeScript("return document.querySelector('macroponent-f51912f4c700201072b211d4d8c26010').shadowRoot.querySelector('sn-polaris-layout').shadowRoot.querySelector('sn-polaris-header').shadowRoot.querySelector('sn-polaris-menu.is-main-menu.is-pinned.can-animate').shadowRoot.querySelector('sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(9) > sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(2) > span > a')");
					((JavascriptExecutor) driver).executeScript("arguments[0].click();", reqtask);
					
					openRecord(logger, requestid, "Request ID");
					util.pause(logger, "10");
					util.scrollByVisibleElement(driver, logger, nav.tab_contractdetails);
					util.clickOn(logger, nav.tab_reviewtasks); 
					util.pause(logger, "5");
					//Open Record
					OpenP55ReviewTask(logger); util.pause(logger, "10"); 
					WebElement reviewtab = driver.findElement(By.xpath("//span[contains(text(),'Review Task')]/parent::span"));
					util.clickOn(logger, reviewtab);
						
					//User confirms travel details
					util.selectBoxByValue(logger, nav.dropdown(driver, "Are the travel details confirmed?", ""), "Yes");
					util.verifyElementByXpath(logger, nav.label(driver, "Recoveries", ""), "Recoveries");
					util.selectBoxByValue(logger, nav.dropdown(driver, "Recoveries", ""), "To be charged");
					util.pause(logger, "5");
						
							
					//<11/25/2021> <Clicking Launch review/Fast track review button to perform saving function> <karen.b.nicolas> <1284806>					
						
						//Update some fields before clicking Launch Review to verify the saving function.
						util.pause(logger, "5");
						util.selectBoxByValue(logger, nav.dropdown(driver, "Policy breach?", ""), "Yes");
						util.setText(logger, nav.text(driver, "Additional comments", ""), "This is a test");

						//User Launches the Review task
						util.pause(logger, "5");
						util.clickOn(logger, nav.button(driver, "Launch Review", "")); util.pause(logger, "10");
						util.verifySelectedValueInDropdown(logger, nav.dropdown(driver, "Review status", ""), "Work in Progress");
						util.verifySelectedValueInDropdown(logger, nav.dropdown(driver, "Policy breach?", ""), "Yes");
						util.verifyExactText(logger, nav.text(driver, "Additional comments", ""), "This is a test");
						
						
						//Update some fields before clicking Fast Track Review to verify the saving function.
						util.pause(logger, "5");
						util.selectBoxByValue(logger, nav.dropdown(driver, "Policy breach?", ""), "No");
						util.clearText(logger, nav.text(driver, "Additional comments", ""));
						util.setText(logger, nav.text(driver, "Additional comments", ""), "Fast track review");
						
						//User clicks Fast Track button
						util.pause(logger, "5");
						util.clickOn(logger, nav.button(driver, "Fast Track Review", "")); util.pause(logger, "7");
						util.verifySelectedValueInDropdown(logger, nav.dropdown(driver, "Policy breach?", ""), "No");
						util.verifyExactText(logger, nav.text(driver, "Additional comments", ""), "Fast track review");
					}
				
					catch (Exception e) {
						util.screenShotAndErrorMsg(logger, e, driver, "Policy 55 Review task is not clicked");
					}			
					extent.endTest(logger);
					extent.flush();	
				}
		@Test
		public void verifyP55Activitylog() {
			ExtentTest logger  = extent.startTest("User verifies P55 Activity log", "User verifies P55 Activity log");
	
				try {	
					util.pause(logger, "5");	
					//user clicks Activities tab
					util.clickByJavascriptExecutor(logger, driver, nav.tab_activities);
					//<1.18.22><[6-009] Notifications: From Optional to Auto-sent><1367931><angelika.perez>
					//verify review launched email notifications to preparer and SME Reviewers are autosent
					LoadAutosentEmailNotificationinActivities(logger, "Your case is now under review: ");
					util.scrollByVisibleElement(driver, logger, nav.label(driver, "Your case is now under review: ", ""));
					util.verifyElementByXpath(logger, nav.label(driver, "Your case is now under review: "+requestid+" - "+getInputData(testName, "Country/location"), ""));
					util.checkForContainsText(logger, nav.launchreviewrequestorrecipient, RequestorEID+"@email.com");
					//verify email notication is autosent to SME reviewers
					util.scrollByVisibleElement(driver, logger, nav.label(driver, "Action Required: Your review is requested for", ""));
					util.verifyElementByXpath(logger, nav.label(driver, "Action Required: Your review is requested for "+requestid, ""));
					
				}
				catch (Exception e) {
					util.screenShotAndErrorMsg(logger, e, driver, "Policy 55 Activitiy log tab is not clicked");
				}		
			extent.endTest(logger);
			extent.flush();

	}
		
		
		@Test
		public void setP55ReviewStatustoApproved() {
			ExtentTest logger  = extent.startTest("User updates P55 review status to Approved", "User updates P55 review status to Approved");
	
				try {	
					util.pause(logger, "5");	
					//user clicks Activities tab
					WebElement reviewtab = driver.findElement(By.xpath("//span[contains(text(),'Review Task')]/parent::span"));
					util.clickOn(logger, reviewtab);
					
					//user selects Approved in the Review status field
					util.selectBoxByValue(logger, nav.reviewstatus, "Approved");
					util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Additional actions", "", "")); util.pause(logger, "2");
					util.clickByJavascriptExecutor(logger, driver, nav.label(driver, "Save", "")); util.pause(logger, "6");
					
				}
				catch (Exception e) {
					util.screenShotAndErrorMsg(logger, e, driver, "Review status is not set to Approved");
				}		
			extent.endTest(logger);
			extent.flush();
		}
		
		
		//<1.19.22><[6-005] Notification to be sent out to resources once travel details are confirmed><1274877><angelika.perez>
		@Test
		public void NotificationstoTravelerwhenReviewisApproved() {
			ExtentTest logger  = extent.startTest("User verifies email notification to travelers", "User verifies email notification to travelers");
	
				try {	
					String FulfillerPassword = getInputData("GLOBAL", "FulfillerPassword");
					String FulfillerEID = getInputData("GLOBAL", "FulfillerEID");
					
					SSOlogin(logger, FulfillerEID, FulfillerPassword, getInputData("GLOBAL", "URL"));
					browserHelper.navigate(logger, getInputData("GLOBAL", "NAVPAGE_URL"));
					util.pause(logger, "10");
					
					//search Table
					List<String> item=new ArrayList<String>();
					util.pause(logger, "10");
			           item.add("Policy 55/ Policy 68 Approval Tool");
			           item.add("Policy 55/68 Request Tasks");
			           shadowDomSearchFilter(logger,item.get(0),item,"Policy 55/ Policy 68 Approval Tool");
					
					// Click the Request task using shadow DOM - hermaine.c.t.canania
			        JavascriptExecutor jse = (JavascriptExecutor) driver;
					WebElement reqtask = (WebElement) jse.executeScript("return document.querySelector('macroponent-f51912f4c700201072b211d4d8c26010').shadowRoot.querySelector('sn-polaris-layout').shadowRoot.querySelector('sn-polaris-header').shadowRoot.querySelector('sn-polaris-menu.is-main-menu.is-pinned.can-animate').shadowRoot.querySelector('sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(9) > sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(2) > span > a')");
					((JavascriptExecutor) driver).executeScript("arguments[0].click();", reqtask);
					
					openRecord(logger, requestid, "Request ID"); util.pause(logger, "12");
					util.verifySelectedValueInDropdown(logger, nav.dropdown(driver, "Request status", ""), "Closed Complete");
					util.scrollByVisibleElement(driver, logger, nav.dropdown(driver, "Opportunity status", ""));
					//change Opportunity status to In progess then Won to trigger email notification to Traveler
					util.selectBoxByValue(logger, nav.dropdown(driver, "Opportunity status", ""), "In progress");
					util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Additional actions", "", ""));util.pause(logger, "2");
					util.clickByJavascriptExecutor(logger, driver, nav.label(driver, "Save", "")); util.pause(logger, "10");
					util.scrollByVisibleElement(driver, logger, nav.dropdown(driver, "Opportunity status", ""));
					util.selectBoxByValue(logger, nav.dropdown(driver, "Opportunity status", ""), "Won");
					util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Additional actions", "", ""));util.pause(logger, "2");
					util.clickByJavascriptExecutor(logger, driver, nav.label(driver, "Save", "")); util.pause(logger, "10");
					
					//add new resource in Resources tab
					String traveler = "y.s.solano.barraza";
					util.scrollByVisibleElement(driver, logger, nav.tab_contractdetails); util.clickByJavascriptExecutor(logger, driver, nav.tab_resources);
					util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "New", "Resources")); util.pause(logger, "10");
					util.selectBoxByValue(logger, nav.dropdown(driver, "Type of resource", ""),"Avanade employees (if seconded)"); util.pause(logger, "5");
					util.setText(logger, nav.text(driver, "Country/location", ""), getInputData(testName, "Country/location"));
					util.setText(logger, nav.text(driver, "Resource EID", ""), traveler);
					util.setText(logger, nav.text(driver, "Onsite presence in the host country/location during the last 12 months", ""), "test");
					nav.traveldates.click(); util.setTextWithEnter(logger, nav.traveldates, "2021-09-06"); util.clickOn(logger, nav.label(driver, "List of travel dates", ""));
					util.clickOn(logger, nav.traveldates); Thread.sleep(1000);
					util.clearText(logger, nav.traveldates); util.setTextWithEnter(logger, nav.traveldates, "2021-09-08");
					util.clickOn(logger, nav.label(driver, "List of travel dates", ""));
					util.clickOn(logger, nav.traveldates); Thread.sleep(1000);
					util.clearText(logger, nav.traveldates); util.pause(logger, "5");
					util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Submit", "")); util.pause(logger, "7");
					
					//edit travel dates of Resource for email verification
					util.scrollByVisibleElement(driver, logger, nav.tab_contractdetails); 
					util.clickByJavascriptExecutor(logger, driver, nav.tab_resources);
					util.pause(logger, "5");
					util.selectBoxByValue(logger, nav.dropdown(driver, "Search","Resources"), "Resource EID");
					util.waitTillElementIsClickable(logger, driver, nav.backgroundText(driver, "Search","Resources"));
					util.setTextWithEnter(logger, nav.backgroundText(driver, "Search","Resources"), traveler);
					
					//Added code for mouse hover to the preview button - hermaine.c.t.canania
					WebElement preview = driver.findElement(By.xpath("//*[contains(@aria-label,'Preview')]/parent::td//a[@data-list_id='x_amspi_policy_request_task.x_amspi_policy_req_resources.task_number']"));
					Actions action = new Actions(driver);
					action.moveToElement(preview).perform();
					
					util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Preview", "", "Resources"));
					util.pause(logger, "5");
					util.clickOn(logger, nav.button(driver, "Open Record", ""));
					util.pause(logger, "10");
					util.setText(logger, nav.traveldates, "clear"); util.clickOn(logger, nav.label(driver, "List of travel dates", ""));
					nav.traveldates.click(); util.setTextWithEnter(logger, nav.traveldates, "2022-01-06"); util.clickOn(logger, nav.label(driver, "List of travel dates", ""));
					util.clickOn(logger, nav.traveldates); Thread.sleep(1000);
					util.clearText(logger, nav.traveldates); util.setTextWithEnter(logger, nav.traveldates, "2022-01-08");
					util.clickOn(logger, nav.label(driver, "List of travel dates", ""));
					util.clickOn(logger, nav.traveldates); Thread.sleep(1000);
					util.clearText(logger, nav.traveldates); util.pause(logger, "5");
					util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Additional actions", "", ""));util.pause(logger, "2");
					util.clickByJavascriptExecutor(logger, driver, nav.label(driver, "Save", "")); util.pause(logger, "5");
					util.scrollByVisibleElement(driver, logger, nav.text(driver, "List of travel dates", ""));
					String traveldates= util.getElementValue(logger, nav.text(driver, "List of travel dates", ""));
					util.pause(logger, "60");
					
					//verify sent emails to travelers
					//email for traveller with edited travel dates
					verifyEmailNotification(logger,traveler ,getInputData(testName, "Delivery Lead"),"AP55 approval "+requestid+" - "
							+getInputData(testName, "Country/location")+" - "+getInputData(testName, "Client name"));
					VerifyEmailbodytoTravelerEditedTravelDates(logger, traveler, requestid, getInputData(testName, "Country/location"),
							getInputData(testName, "Client name"), traveldates);
					//email for new traveller
					util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Back", "", "")); util.pause(logger, "7");
					util.clickByJavascriptExecutor(logger, driver, driver.findElement(By.xpath("//tr[3]//td[2]//a[1]"))); util.pause(logger, "3");
					util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Open Record", "")); util.pause(logger, "10");
					util.scrollByVisibleElement(driver, logger, nav.text(driver, "Subject", ""));
					util.checkForContainsText(logger, nav.text(driver, "Subject", ""), "AP55 approval "+requestid+" - "
							+getInputData(testName, "Country/location")+" - "+getInputData(testName, "Client name"));
					util.checkForContainsText(logger, nav.text(driver, "Recipients", ""), traveler);
//					util.checkForContainsText(logger, nav.text(driver, "Copied", ""), getInputData(testName, "Delivery Lead"));
					VerifyEmailbodytoTravelers(logger, traveler, requestid, getInputData(testName, "Country/location"),
							getInputData(testName, "Client name"), traveldates);
					//verify email is also autosent for previous traveller(added in requestor form)
					verifyEmailNotification(logger,getInputData(testName, "Resource EID") ,getInputData(testName, "Delivery Lead"),"AP55 approval "+requestid+" - "
							+getInputData(testName, "Country/location")+" - "+getInputData(testName, "Client name"));
					
					
					
				}
				catch (Exception e) {
					util.screenShotAndErrorMsg(logger, e, driver, "Policy 55 Activitiy log tab is not clicked");
				}		
			extent.endTest(logger);
			extent.flush();

	}
		
				
		@Test
		public void NavigateToAllPolicyReviewTask() {
			ExtentTest logger = extent.startTest("Navigate to All Policy 55/68 Review Task", "Navigate to All Policy 55/68 Review Task");
		
			try {	
				
				UserLoginAsFulfiller();
				
//				searchTable(logger, "All Policy 55/68 Review Tasks","Policy 55/ Policy 68 Approval Tool","All Policy 55/68 Review Tasks");
				List<String> item=new ArrayList<String>();
				util.pause(logger, "10");
		           item.add("Policy 55/ Policy 68 Approval Tool");
		           item.add("Policy 55/68 Request Tasks");
		           shadowDomSearchFilter(logger,item.get(0),item,"Policy 55/ Policy 68 Approval Tool");
				
				// Click the Request task using shadow DOM - hermaine.c.t.canania
				JavascriptExecutor jse = (JavascriptExecutor) driver;
				WebElement revtask = (WebElement) jse.executeScript("return document.querySelector('macroponent-f51912f4c700201072b211d4d8c26010').shadowRoot.querySelector('sn-polaris-layout').shadowRoot.querySelector('sn-polaris-header').shadowRoot.querySelector('sn-polaris-menu.is-main-menu.is-pinned.can-animate').shadowRoot.querySelector('sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(10) > sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(2) > span > a')");
				((JavascriptExecutor) driver).executeScript("arguments[0].click();", revtask);
				util.pause(logger, "10");					
			}			
			catch (Exception e) {
				util.screenShotAndErrorMsg(logger, e, driver, "All Policy 55/68 Review Tasks is not displayed");
			}
			extent.endTest(logger);
			extent.flush();
		}
		
		//<12/3/2021> <Related Lists - All Conditions view under Review task> <karen.b.nicolas> <1274799>
		@Test
		public void VerifyOpportunityRequestConditionsViewRelatedList() {
			ExtentTest logger  = extent.startTest("Verify Opportunity Request Conditions View Related List", "Verify To Opportunity Request Conditions View Related List");
			
				try {
					//Open created Opportunity Request
					openRecord(logger, requestid, "Task Number Request ID");
					util.pause(logger, "10"); util.clickByJavascriptExecutor(logger, driver, nav.conditionLink(driver, "Review Task", ""));
							
					//Verify the All Conditions tab related list beside the Corporate Function Reviews.
					util.pause(logger, "5");
					util.scrollByVisibleElement(driver, logger, nav.label(driver, "Corporate Function Reviews", ""));
					util.verifyElementByXpath(logger, driver.findElement(By.xpath("//div[@id='tabs2_list']/span[1]/span")));
					util.verifyElementByXpath(logger, driver.findElement(By.xpath("//div[@id='tabs2_list']/span[2]/span")));
								
								
					//Verify the Escalate to Column is displayed beside the Reviewer(s) Column in default list view.
					verifyReviewerColumns(logger, "Corporate function"); util.pause(logger, "5");
					verifyReviewerColumns(logger, "Escalate to"); util.pause(logger, "5");
					verifyReviewerColumns(logger, "Corporate function review status");
					util.pause(logger, "5");
					verifyReviewerColumns(logger, "Review completion date");
					util.pause(logger, "5");
					verifyReviewerColumns(logger, "Active(u_active)");
					util.pause(logger, "5");
								
					openRecord1(logger, "Global Tax", "Corporate function");
					util.pause(logger, "10");
								
					//Verify the fields available in the existing Corporate Function Review.
					util.scrollByVisibleElement(driver, logger, nav.mandatoryField(driver, "Corporate function", ""));
					util.verifyElementByXpath(logger, nav.mandatoryField(driver, "Corporate function", ""));
					util.pause(logger, "10");
								
					util.verifyElementByXpath(logger, nav.mandatoryField(driver, "Corporate function review status", ""));
					util.verifyElementByXpath(logger, nav.label(driver, "Review completion date", ""));
					util.verifyElementByXpath(logger, nav.checkbox(driver, "Active", ""));
					util.verifyElementByXpath(logger, nav.conditionLink(driver, "Unlock Reviewer(s)", ""));
					util.verifyElementByXpath(logger, nav.conditionLink(driver, "Unlock Escalate to", ""));
								
					//Verify buttons available in the form.
					//Submit button
					util.scrollByVisibleElement(driver, logger, nav.button(driver, "Update", ""));
					util.verifyElementByXpath(logger, nav.button(driver, "Update", ""));
					util.pause(logger, "10");
								
					util.verifyElementByXpath(logger, nav.button(driver, "Link to the Request", ""));
					util.verifyElementByXpath(logger, nav.button(driver, "Link to the Review", ""));

					WebElement Back1 = driver.findElement(By.xpath("//button[@data-original-title='Back']"));
					util.clickOn(logger, Back1);
					util.pause(logger, "10");
								
					//Verify New button is available.
					util.verifyElementByXpath(logger, nav.button(driver, "New", ""));
					util.waitTillElementIsClickable(logger, driver, nav.button(driver, "New", ""));
					util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "New", ""));
					util.pause(logger, "5");
								
					//Verify the fields available in the form.
					util.scrollByVisibleElement(driver, logger, nav.mandatoryField(driver, "Corporate function", ""));
					util.verifyElementByXpath(logger, nav.mandatoryField(driver, "Corporate function", ""));
					util.pause(logger, "10");
								
					util.verifyElementByXpath(logger, nav.mandatoryField(driver, "Corporate function review status", ""));
					util.verifyElementByXpath(logger, nav.label(driver, "Review completion date", ""));
					util.verifyElementByXpath(logger, nav.checkbox(driver, "Active", ""));
					util.verifyElementByXpath(logger, nav.conditionLink(driver, "Unlock Reviewer(s)", ""));
					util.verifyElementByXpath(logger, nav.conditionLink(driver, "Unlock Escalate to", ""));

					//Verify buttons available in the form.
					//Submit button
					util.scrollByVisibleElement(driver, logger, nav.button(driver, "Submit", ""));
					util.verifyElementByXpath(logger, nav.button(driver, "Submit", ""));
					util.pause(logger, "10");
								
					util.verifyElementByXpath(logger, nav.button(driver, "Link to the Request", ""));
					util.verifyElementByXpath(logger, nav.button(driver, "Link to the Review", ""));

					WebElement Back = driver.findElement(By.xpath("//button[@data-original-title='Back']"));
					util.clickOn(logger, Back);
					util.pause(logger, "10");
							
//					WebElement Discard = driver.findElement(By.xpath("//button[@data-action='discard']"));
//					util.clickOn(logger, Discard);
					util.pause(logger, "10");
								
					//Verify All Conditions related list by corporate function and can view the Conditions form once clicked.
					util.scrollByVisibleElement(driver, logger, nav.tab_allconditions);
					util.verifyElementByXpath(logger, nav.tab_allconditions);
					util.clickByJavascriptExecutor(logger, driver, nav.tab_allconditions);
					util.pause(logger, "5");

					//Verify default filter "Conditions > Active = true".
					util.verifyElementByXpath(logger, driver.findElement(By.id("x_amspi_policy_req_review_task_v2.REL:354ba818db5ffc90c3a3ea7b039619cf_breadcrumb")));
					util.pause(logger, "5");

					//Verify Default columns.
					util.waitTillElementIsClickable(logger, driver, nav.lnk_personalizelist);
					util.clickOn(logger, nav.lnk_personalizelist);
				    util.pause(logger, "5");
								
				    util.waitTillElementIsVisible(logger, driver, nav.dropdown(driver, "Available",""));
					util.verifyElementByXpath(logger, nav.dropdown(driver, "Available", ""));
					util.verifyElementByXpath(logger, nav.dropdown(driver, "Selected", ""));
														
					util.verifyElementByXpath(logger, nav.dropdown(driver, "Corporate Function", ""));
					util.clickByJavascriptExecutor(logger, driver, driver.findElement(By.xpath("//*[@id='slush_right']/option[1]")));

					util.verifyElementByXpath(logger, nav.dropdown(driver, "Conditions", ""));
					util.clickByJavascriptExecutor(logger, driver, driver.findElement(By.xpath("//*[@id='slush_right']/option[2]")));

					util.verifyElementByXpath(logger, nav.dropdown(driver, "Active", ""));
					util.clickByJavascriptExecutor(logger, driver, driver.findElement(By.xpath("//*[@id='slush_right']/option[3]")));

					util.verifyElementByXpath(logger, nav.dropdown(driver, "Order", ""));
					util.clickByJavascriptExecutor(logger, driver, driver.findElement(By.xpath("//*[@id='slush_right']/option[4]")));

					WebElement OK = driver.findElement(By.id("ok_button"));
					util.clickOn(logger, OK);
					util.pause(logger, "10");

					//Verify New button is available.
					util.verifyElementByXpath(logger, nav.button(driver, "New", ""));
					util.pause(logger, "5");

						
					}
				catch (Exception e) {
				util.screenShotAndErrorMsg(logger, e, driver, "Unable Verify Approved Notifications Received By Opportunity Director");
			}		
			extent.endTest(logger);
			extent.flush();
				
						}
			
		//<12/1/2021> <[6-012] AP55 - Approved Email Notifications are received by Opp Director when Opp Status is in progress> <karen.b.nicolas> <1571559>
		@Test
			public void VerifyAP55ReviewTasksApprovedCompletedNotificationsReceivedByOppDirector() {
				ExtentTest logger  = extent.startTest("Verify AP55 Review Tasks Approved and Completed Notifications Received By Opportunity Director", "Verify To AP55 Review Tasks Approved and Completed Notifications Received By Opportunity Director");
				
							try {
								String FulfillerPassword = getInputData("GLOBAL", "FulfillerPassword");
								String FulfillerEID = getInputData("GLOBAL", "FulfillerEID");
								
								SSOlogin(logger, FulfillerEID, FulfillerPassword, getInputData("GLOBAL", "URL"));
								browserHelper.navigate(logger, getInputData("GLOBAL", "NAVPAGE_URL"));
								util.pause(logger, "10");
								
								//search Table
								List<String> item=new ArrayList<String>();
								util.pause(logger, "10");
						           item.add("Policy 55/ Policy 68 Approval Tool");
						           item.add("Policy 55/68 Request Tasks");
						           shadowDomSearchFilter(logger,item.get(0),item,"Policy 55/ Policy 68 Approval Tool");
								
								// Click the Request task using shadow DOM - hermaine.c.t.canania
						        JavascriptExecutor jse = (JavascriptExecutor) driver;
								WebElement reqtask = (WebElement) jse.executeScript("return document.querySelector('macroponent-f51912f4c700201072b211d4d8c26010').shadowRoot.querySelector('sn-polaris-layout').shadowRoot.querySelector('sn-polaris-header').shadowRoot.querySelector('sn-polaris-menu.is-main-menu.is-pinned.can-animate').shadowRoot.querySelector('sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(9) > sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(2) > span > a')");
								((JavascriptExecutor) driver).executeScript("arguments[0].click();", reqtask);
								
								openRecord(logger, requestid, "Request ID"); 
								util.pause(logger, "12");
								
								//verify Opportunity status is In progress
								util.scrollByVisibleElement(driver, logger, nav.dropdown(driver, "Opportunity status", ""));
								util.verifySelectedValueInDropdown(logger, nav.dropdown(driver, "Opportunity status", ""), "In progress");
								logger.log(LogStatus.PASS, "Opportunity status is In progress");
								util.scrollByVisibleElement(driver, logger, nav.text(driver, "Opportunity Director", ""));
								String Oppdirector = util.getElementValue(logger, nav.text(driver, "Opportunity Director", ""));
								
								//open AP55 Review task
								util.scrollByVisibleElement(driver, logger, nav.tab_contractdetails);
								util.clickByJavascriptExecutor(logger, driver, nav.tab_reviewtasks); util.pause(logger, "5");
								OpenP55ReviewTask(logger); util.pause(logger, "5"); 
								WebElement Reviewtask = driver.findElement(By.xpath("//div[@id='tabs2_section']//span[contains(text(), 'Review Task')]"));
								util.clickByJavascriptExecutor(logger, driver, Reviewtask);
								util.scrollByVisibleElement(driver, logger, nav.dropdown(driver, "Review status", ""));
								util.selectBoxByValue(logger, nav.dropdown(driver, "Review status", ""), "Work in Progress");
								util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Additional actions", "", "")); util.pause(logger, "2");
								util.clickByJavascriptExecutor(logger, driver, nav.label(driver, "Save", "")); util.pause(logger, "10");
								
								//set review to Approved and verify email notification to Opportunity Director
								util.scrollByVisibleElement(driver, logger, nav.dropdown(driver, "Review status", ""));
								util.selectBoxByValue(logger, nav.dropdown(driver, "Review status", ""), "Approved");
								util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Additional actions", "", "")); util.pause(logger, "2");
								util.clickByJavascriptExecutor(logger, driver, nav.label(driver, "Save", "")); util.pause(logger, "10");
								util.clickByJavascriptExecutor(logger, driver, nav.tab_activities);
								util.scrollByVisibleElement(driver, logger, driver.findElement(By.xpath("//li//span[contains(text(),'has been Approved')]")));
								util.checkForContainsText(logger, driver.findElement(By.xpath("//li//span[contains(text(),'has been Approved')]//following::li[2]//span[2]")), Oppdirector+"@accenture.com");
								logger.log(LogStatus.PASS, "Approved email notification is sent to Opportunity Director");
								
								//set review to Completed and send email notification to Opportunity Director
								String currentWindow = getCurrentWindow();
								util.clickByJavascriptExecutor(logger, driver, driver.findElement(By.xpath("//div[@id='tabs2_section']//span[contains(text(), 'Review Task')]")));
								util.scrollByVisibleElement(driver, logger, nav.dropdown(driver, "Review status", ""));
								util.selectBoxByValue(logger, nav.dropdown(driver, "Review status", ""), "Completed");
								util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Additional actions", "", "")); util.pause(logger, "2");
								util.clickByJavascriptExecutor(logger, driver, nav.label(driver, "Save", "")); util.pause(logger, "10");
								util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "More options", "", ""));
								util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Email", "")); 
								
								//switch window	
								String parentHandle = frameHelper.getParentWindowHandle(logger, driver);
								util.pause(logger, "5");
								frameHelper.switchToChildWindow(logger, driver, parentHandle);
								
								util.pause(logger, "20"); util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Send", "")); util.pause(logger, "15");
								
								//verify sent completed email notification to Opportunity Director
								String FulfillerPassword1 = getInputData("GLOBAL", "FulfillerPassword");
								String FulfillerEID1 = getInputData("GLOBAL", "FulfillerEID");
								
								SSOlogin(logger, FulfillerEID1, FulfillerPassword1, getInputData("GLOBAL", "URL"));
								browserHelper.navigate(logger, getInputData("GLOBAL", "NAVPAGE_URL"));
								util.pause(logger, "10");

								//search Table
								List<String> item1=new ArrayList<String>();
								util.pause(logger, "10");
						           item1.add("Policy 55/ Policy 68 Approval Tool");
						           item1.add("Policy 55/68 Request Tasks");
						           shadowDomSearchFilter(logger,item1.get(0),item1,"Policy 55/ Policy 68 Approval Tool");
								
								// Click the Request task using shadow DOM - hermaine.c.t.canania
						        JavascriptExecutor jse1 = (JavascriptExecutor) driver;
								WebElement reqtask1 = (WebElement) jse1.executeScript("return document.querySelector('macroponent-f51912f4c700201072b211d4d8c26010').shadowRoot.querySelector('sn-polaris-layout').shadowRoot.querySelector('sn-polaris-header').shadowRoot.querySelector('sn-polaris-menu.is-main-menu.is-pinned.can-animate').shadowRoot.querySelector('sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(9) > sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(2) > span > a')");
								((JavascriptExecutor) driver).executeScript("arguments[0].click();", reqtask1);
								
								openRecord(logger, requestid, "Request ID"); util.pause(logger, "12");
								util.scrollByVisibleElement(driver, logger, nav.tab_contractdetails);
								util.clickByJavascriptExecutor(logger, driver, nav.tab_reviewtasks); util.pause(logger, "5");
								OpenP55ReviewTask(logger); util.pause(logger, "10"); util.clickByJavascriptExecutor(logger, driver, nav.tab_activities);
								util.scrollByVisibleElement(driver, logger, driver.findElement(By.xpath("//li//span[contains(text(),'has been Completed')]")));
								util.checkForContainsText(logger, driver.findElement(By.xpath("//li//span[contains(text(),'has been Completed')]//following::li[2]//span[2]")), Oppdirector+"@accenture.com");
								logger.log(LogStatus.PASS, "Completed email notification is sent to Opportunity Director");

							}
							catch (Exception e) {
								util.screenShotAndErrorMsg(logger, e, driver, "Unable to verify AP55 Review Tasks Approved Notifications Received By Opportunity Director");
							}		
								extent.endTest(logger);
								extent.flush();
					
							}
					
					
				
					
					@Test
					public void closedComplete() {
						ExtentTest logger  = extent.startTest("User verifies Closed Complete request", "User verifies Closed Complete request");
				
							try {	
								String FulfillerPassword = getInputData("GLOBAL", "FulfillerPassword");
								String FulfillerEID = getInputData("GLOBAL", "FulfillerEID");
								
								SSOlogin(logger, FulfillerEID, FulfillerPassword, getInputData("GLOBAL", "URL"));
								browserHelper.navigate(logger, getInputData("GLOBAL", "NAVPAGE_URL"));
								util.pause(logger, "10");
								
								//search Table
								List<String> item=new ArrayList<String>();
								util.pause(logger, "10");
						           item.add("Policy 55/ Policy 68 Approval Tool");
						           item.add("Policy 55/68 Request Tasks");
						           shadowDomSearchFilter(logger,item.get(0),item,"Policy 55/ Policy 68 Approval Tool");
								
								// Click the Request task using shadow DOM - hermaine.c.t.canania
						        JavascriptExecutor jse = (JavascriptExecutor) driver;
								WebElement reqtask = (WebElement) jse.executeScript("return document.querySelector('macroponent-f51912f4c700201072b211d4d8c26010').shadowRoot.querySelector('sn-polaris-layout').shadowRoot.querySelector('sn-polaris-header').shadowRoot.querySelector('sn-polaris-menu.is-main-menu.is-pinned.can-animate').shadowRoot.querySelector('sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(9) > sn-collapsible-list').shadowRoot.querySelector('div > div > ul > li:nth-child(2) > span > a')");
								((JavascriptExecutor) driver).executeScript("arguments[0].click();", reqtask);
								
								openRecord(logger,requestid,"Request ID"); util.pause(logger, "10");
								
								//user verifies closed complete status
								util.pause(logger, "5");	
								util.verifySelectedValueInDropdown(logger, nav.dropdown(driver, "Request status", ""), "Closed Complete");
																
								//user clicks reopen case button
								util.pause(logger, "5");
								util.clickOn(logger, nav.button(driver, "Reopen Case", ""));
								
								//user verifies status after reopening case
								util.pause(logger, "5");
								openRecord1(logger,requestid,"Request ID");
								
								util.verifySelectedValueInDropdown(logger, nav.dropdown(driver, "Request status", ""), "Ready");
								
								//change Opportunity ID to reuse valid Opportunity ID
								util.scrollByVisibleElement(driver, logger, nav.text(driver, "Opportunity ID", ""));
								util.clearText(logger, nav.text(driver, "Opportunity ID", ""));
								util.setText(logger, nav.text(driver, "Opportunity ID", ""), "1234554321");
								util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Update", ""));
								
							}
							catch (Exception e) {
								util.screenShotAndErrorMsg(logger, e, driver, "Review status is not set to Approved");
							}		
						extent.endTest(logger);
						extent.flush();
					}
					
					//<1/14/2022> <[6-011] Notifications - add a Do Not Reply note> <karen.b.nicolas> <1523567>
					@Test
					public void VerifyOpportunityRequestWithNoMMSIDNotificationAddADoNotReplyNote() {
							ExtentTest logger = extent.startTest("Verify Opportunity Request No MMSID Notification Add A Do Not Reply Note", "Verify Opportunity Request No MMSID Notification Add A Do Not Reply Note");
							try {
								String FulfillerEID = getInputData("GLOBAL", "FulfillerEID");
								String Password = getInputData("GLOBAL", "Password");

								navigateFulfiller(logger);
								initializePage();
								util.pause(logger, "10");
								util.waitTillElementIsVisible(logger, driver, login.username);
								login.login(logger, FulfillerEID, Password);
								util.pause(logger, "10");
							
								browserHelper.navigate(logger, getInputData("GLOBAL", "NAVPAGE_URL"));
								util.pause(logger, "10");
								
								util.waitTillElementIsClickable(logger, driver, nav.backgroundText(driver, "Filter navigator",""));
//								searchTable(logger, "All Policy 55/68 Request Tasks","Policy 55/ Policy 68 Approval Tool","All Policy 55/68 Request Tasks");
								List<String> item=new ArrayList<String>();
								util.pause(logger, "10");
						           item.add("Policy 55/ Policy 68 Approval Tool");
						           item.add("Policy 55/68 Request Tasks");
						           shadowDomSearchFilter(logger,item.get(0),item,"Policy 55/ Policy 68 Approval Tool");
								
								// Click the Request task using shadow DOM - hermaine.c.t.canania
								JavascriptExecutor jse = (JavascriptExecutor) driver;
								WebElement reqtask = (WebElement) jse.executeScript("return document.querySelector(\"macroponent-f51912f4c700201072b211d4d8c26010\").shadowRoot.querySelector(\"sn-polaris-layout\").shadowRoot.querySelector(\"sn-polaris-header\").shadowRoot.querySelector(\"sn-polaris-menu.is-main-menu.is-pinned.can-animate\").shadowRoot.querySelector(\"sn-collapsible-list:nth-child(1)\").shadowRoot.querySelector(\"div > div > ul > li:nth-child(10) > sn-collapsible-list\").shadowRoot.querySelector(\"div > div > ul > li:nth-child(2) > span > a > span > span\")");
								((JavascriptExecutor) driver).executeScript("arguments[0].click();", reqtask);
								
								util.pause(logger, "10");	
								
								driver.findElement(By.xpath("//b[normalize-space()='All']")).click();
								openRecord(logger,requestid1,"Request ID");
								util.pause(logger, "10");
								
								
								//Verify Opportunity Request with 'No' MMS ID. Request for additional Information - Notification to Preparer.
								util.verifyElementByXpath(logger, nav.mandatoryField(driver, "Business pre-approval?", ""));
								util.verifyElementByXpath(logger, nav.dropdown(driver, "Business pre-approval?", ""));
								util.selectBoxByValue(logger, nav.dropdown(driver, "Business pre-approval?", ""), "No");
								util.pause(logger, "5");
								
								WebElement Coordinatorcomments = driver.findElement(By.id("x_amspi_policy_request_task.x_amspi_policy_req_u_coordinator_comments"));
								Coordinatorcomments.sendKeys("For testing only.");
								util.pause(logger, "5");
								
								util.scrollByVisibleElement(driver, logger, nav.button(driver, "Request for additional information", ""));
								util.verifyElementByXpath(logger, nav.button(driver, "Request for additional information", ""));
								util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Request for additional information", ""));
								util.pause(logger, "5");
								
								openRecord(logger,requestid1,"Request ID");
								util.pause(logger, "10");

								util.scrollByVisibleElement(driver, logger, nav.tab_Activities);
								util.verifyElementByXpath(logger, nav.tab_Activities);
								util.clickByJavascriptExecutor(logger, driver, nav.tab_Activities);
								util.pause(logger, "5");
								
								util.waitTillElementIsVisible(logger, driver, nav.link(driver, "Show email details", ""));
								
								Actions actions = new Actions(driver);
								actions.contextClick(nav.link(driver, "Show email details", "")).perform();
								clickDownThenEnter();
								frameHelper.switchToChildWindow(logger, driver,frameHelper.getParentWindowHandle(logger, driver) );
								Thread.sleep(15000);
								
								//Verify the Notifications - add a Do Not Reply note.
								util.waitTillElementIsVisible(logger, driver, nav.label(driver, "This is an automated system generated e-mail. Response to this email is not supported.", ""));
								util.checkForContainsText(logger, nav.label(driver, "This is an automated system generated e-mail. Response to this email is not supported.", ""), "This is an automated system generated e-mail. Response to this email is not supported.");
								util.verifyElementByXpath(logger, nav.label(driver, "This is an automated system generated e-mail. Response to this email is not supported.", ""));
								util.pause(logger, "10");
								
								//Verify if the email notification sent to the preparer.				
								util.scrollByVisibleElement(driver, logger, nav.label(driver, "To: angelika.perez", ""));
								util.checkForContainsText(logger, nav.label(driver, "To: angelika.perez", ""), "To: angelika.perez");
								util.verifyElementByXpath(logger, nav.label(driver, "To: angelika.perez", ""));
								util.pause(logger, "10");

								}
								catch (Exception e) {
										util.screenShotAndErrorMsg(logger, e, driver, "Unable to verify notifications with Do not reply email content");

								}
										extent.endTest(logger);
										extent.flush();
										driver.close();
								}

					
						//<1/14/2022> <[6-011] Notifications - add a Do Not Reply note> <karen.b.nicolas> <1523567>
						@Test
						public void VerifyOpportunityRequestWithMMSIDNotificationAddADoNotReplyNote() {
								ExtentTest logger = extent.startTest("Verify Opportunity Request With MMSID Notification Add A Do Not Reply Note", "Verify Opportunity Request With MMSID Notification Add A Do Not Reply Note");
								try {
								
									String FulfillerEID = getInputData("GLOBAL", "FulfillerEID");
									String Password = getInputData("GLOBAL", "Password");

									navigateFulfiller(logger);
									initializePage();
									util.pause(logger, "10");
									util.waitTillElementIsVisible(logger, driver, login.username);
									login.login(logger, FulfillerEID, Password);
									util.pause(logger, "10");
								
									browserHelper.navigate(logger, getInputData("GLOBAL", "NAVPAGE_URL"));
									util.pause(logger, "10");
									
									util.waitTillElementIsClickable(logger, driver, nav.backgroundText(driver, "Filter navigator",""));
//									searchTable(logger, "All Policy 55/68 Request Tasks","Policy 55/ Policy 68 Approval Tool","All Policy 55/68 Request Tasks");
									List<String> item=new ArrayList<String>();
									util.pause(logger, "10");
							           item.add("Policy 55/ Policy 68 Approval Tool");
							           item.add("Policy 55/68 Request Tasks");
							           shadowDomSearchFilter(logger,item.get(0),item,"Policy 55/ Policy 68 Approval Tool");
									
									// Click the Request task using shadow DOM - hermaine.c.t.canania
									JavascriptExecutor jse = (JavascriptExecutor) driver;
									WebElement reqtask = (WebElement) jse.executeScript("return document.querySelector(\"macroponent-f51912f4c700201072b211d4d8c26010\").shadowRoot.querySelector(\"sn-polaris-layout\").shadowRoot.querySelector(\"sn-polaris-header\").shadowRoot.querySelector(\"sn-polaris-menu.is-main-menu.is-pinned.can-animate\").shadowRoot.querySelector(\"sn-collapsible-list:nth-child(1)\").shadowRoot.querySelector(\"div > div > ul > li:nth-child(10) > sn-collapsible-list\").shadowRoot.querySelector(\"div > div > ul > li:nth-child(2) > span > a > span > span\")");
									((JavascriptExecutor) driver).executeScript("arguments[0].click();", reqtask);
									
									util.pause(logger, "10");

									driver.findElement(By.xpath("//b[normalize-space()='All']")).click();
									openRecord(logger,requestid2,"Request ID");
									util.pause(logger, "10");
									
									
									//Verify Opportunity Request with 'No' MMS ID. Request for Review Approved 1 - Notification to Opportunity director.
									util.scrollByVisibleElement(driver, logger, nav.tab_reviewtasks);
									util.verifyElementByXpath(logger, nav.tab_reviewtasks);
									util.clickByJavascriptExecutor(logger, driver, nav.tab_reviewtasks);
									util.pause(logger, "10");
									
									util.clickByJavascriptExecutor(logger, driver, nav.recordAP68);
									util.pause(logger, "5");
									util.waitTillElementIsClickable(logger, driver, nav.link(driver, "Open Record", ""));
									util.clickByJavascriptExecutor(logger, driver, nav.link(driver, "Open Record", ""));
									util.pause(logger, "5");
									

									util.scrollByVisibleElement(driver, logger, nav.policybreachfield);
									util.verifyElementByXpath(logger, nav.policybreachfield);
									util.selectBoxByValue(logger, nav.policybreachfield, "No");
									util.pause(logger, "10");
									
									util.scrollByVisibleElement(driver, logger, nav.reviewstatusfield);
									util.verifyElementByXpath(logger, nav.reviewstatusfield);
									util.selectBoxByValue(logger, nav.reviewstatusfield, "Approved");
									util.pause(logger, "10");

									util.scrollByVisibleElement(driver, logger, nav.button(driver, "Update", ""));
									util.verifyElementByXpath(logger, nav.button(driver, "Update", ""));
									util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Update", ""));
									util.pause(logger, "10");
									
									util.scrollByVisibleElement(driver, logger, nav.tab_reviewtasks);
									util.verifyElementByXpath(logger, nav.tab_reviewtasks);
									util.clickByJavascriptExecutor(logger, driver, nav.tab_reviewtasks);
									util.pause(logger, "10");
									
									util.clickByJavascriptExecutor(logger, driver, nav.recordAP68);
									util.pause(logger, "5");
									util.waitTillElementIsClickable(logger, driver, nav.link(driver, "Open Record", ""));
									util.clickByJavascriptExecutor(logger, driver, nav.link(driver, "Open Record", ""));
									util.pause(logger, "5");
									

									util.scrollByVisibleElement(driver, logger, nav.tab_activities);
									util.verifyElementByXpath(logger, nav.tab_activities);
									util.clickByJavascriptExecutor(logger, driver, nav.tab_activities);
									util.pause(logger, "5");
									
									util.scrollByVisibleElement(driver, logger, nav.lnk_additionalactions);
									util.verifyElementByXpath(logger, nav.lnk_additionalactions);
									util.clickByJavascriptExecutor(logger, driver, nav.lnk_additionalactions);
									util.pause(logger, "5");
									
									util.scrollByVisibleElement(driver, logger, nav.lnk_reloadform);
									util.verifyElementByXpath(logger, nav.lnk_reloadform);
									util.clickByJavascriptExecutor(logger, driver, nav.lnk_reloadform);
									util.pause(logger, "10");
									
									util.scrollByVisibleElement(driver, logger, nav.lnk_additionalactions);
									util.verifyElementByXpath(logger, nav.lnk_additionalactions);
									util.clickByJavascriptExecutor(logger, driver, nav.lnk_additionalactions);
									util.pause(logger, "5");
									
									util.scrollByVisibleElement(driver, logger, nav.lnk_reloadform);
									util.verifyElementByXpath(logger, nav.lnk_reloadform);
									util.clickByJavascriptExecutor(logger, driver, nav.lnk_reloadform);
									util.pause(logger, "10");
									
									util.waitTillElementIsVisible(logger, driver, nav.link(driver, "Show email details", ""));
									util.clickByJavascriptExecutor(logger, driver, nav.link(driver, "Show email details", ""));
									util.pause(logger, "10");
									
									util.verifyExactText(logger, driver.findElement(By.xpath("//*[@id='sn_form_inline_stream_entries']/ul/li[1]/div[3]/div/ul/li[4]/span[2]")), "a.cardone@accenture.com");
									util.pause(logger, "10");
									
									util.waitTillElementIsVisible(logger, driver, nav.link(driver, "Hide email details", ""));
									util.clickByJavascriptExecutor(logger, driver, nav.link(driver, "Hide email details", ""));
									util.pause(logger, "10");
									
									util.waitTillElementIsVisible(logger, driver, nav.link(driver, "Show email details", ""));
									util.pause(logger, "10");
								
									Actions actions = new Actions(driver);
									actions.contextClick(nav.link(driver, "Show email details", "")).perform();
									clickDownThenEnter();
									frameHelper.switchToChildWindow(logger, driver,frameHelper.getParentWindowHandle(logger, driver) );
									Thread.sleep(10000);
									
									//Verify the Notifications - add a Do Not Reply note.
									util.waitTillElementIsVisible(logger, driver, nav.label(driver, "This is an automated system generated e-mail. Response to this email is not supported.", ""));
									util.checkForContainsText(logger, nav.label(driver, "This is an automated system generated e-mail. Response to this email is not supported.", ""), "This is an automated system generated e-mail. Response to this email is not supported.");
									util.verifyElementByXpath(logger, nav.label(driver, "This is an automated system generated e-mail. Response to this email is not supported.", ""));
									util.pause(logger, "10");

									
									}
									catch (Exception e) {
											util.screenShotAndErrorMsg(logger, e, driver, "Unable to verify notifications with Do not reply email content.");

									}
											extent.endTest(logger);
											extent.flush();
											driver.close();
									}
						
								//<1/14/2022> <[6-011] Notifications - add a Do Not Reply note> <karen.b.nicolas> <1523567>
								@Test
								public void VerifyRemoteWorkExceptionRequestNotificationAddADoNotReplyNote() {
										ExtentTest logger = extent.startTest("Verify Remote Work Exception Request Notification Add A Do Not Reply Note", "Verify Remote Work Exception Request Notification Add A Do Not Reply Note");
										try {
											
											String FulfillerEID = getInputData("GLOBAL", "FulfillerEID");
											String Password = getInputData("GLOBAL", "Password");

											navigateFulfiller(logger);
											initializePage();
											util.pause(logger, "10");
											util.waitTillElementIsVisible(logger, driver, login.username);
											login.login(logger, FulfillerEID, Password);
											util.pause(logger, "10");
										
											browserHelper.navigate(logger, getInputData("GLOBAL", "NAVPAGE_URL"));
											util.pause(logger, "10");
											
											util.waitTillElementIsClickable(logger, driver, nav.backgroundText(driver, "Filter navigator",""));
//											searchTable(logger, "All Policy 55/68 Request Tasks","Policy 55/ Policy 68 Approval Tool","All Policy 55/68 Request Tasks");
											List<String> item=new ArrayList<String>();
											util.pause(logger, "10");
									           item.add("Policy 55/ Policy 68 Approval Tool");
									           item.add("Policy 55/68 Request Tasks");
									           shadowDomSearchFilter(logger,item.get(0),item,"Policy 55/ Policy 68 Approval Tool");
											
											// Click the Request task using shadow DOM - hermaine.c.t.canania
											JavascriptExecutor jse = (JavascriptExecutor) driver;
											WebElement reqtask = (WebElement) jse.executeScript("return document.querySelector(\"macroponent-f51912f4c700201072b211d4d8c26010\").shadowRoot.querySelector(\"sn-polaris-layout\").shadowRoot.querySelector(\"sn-polaris-header\").shadowRoot.querySelector(\"sn-polaris-menu.is-main-menu.is-pinned.can-animate\").shadowRoot.querySelector(\"sn-collapsible-list:nth-child(1)\").shadowRoot.querySelector(\"div > div > ul > li:nth-child(10) > sn-collapsible-list\").shadowRoot.querySelector(\"div > div > ul > li:nth-child(2) > span > a > span > span\")");
											((JavascriptExecutor) driver).executeScript("arguments[0].click();", reqtask);
											
											util.pause(logger, "10");
											
											driver.findElement(By.xpath("//b[normalize-space()='All']")).click();
											openRecord(logger,requestid3,"Request ID");
											util.pause(logger, "10");
											
											
											//Verify Opportunity Request with 'No' MMS ID. Request for Review Approved - Notification to Home Mobility Lead.
											util.scrollByVisibleElement(driver, logger, nav.tab_reviewtasksWFH);
											util.verifyElementByXpath(logger, nav.tab_reviewtasksWFH);
											util.clickByJavascriptExecutor(logger, driver, nav.tab_reviewtasksWFH);
											util.pause(logger, "10");
											
											util.clickByJavascriptExecutor(logger, driver, nav.recordAP55);
											util.pause(logger, "5");
											util.waitTillElementIsClickable(logger, driver, nav.link(driver, "Open Record", ""));
											util.clickByJavascriptExecutor(logger, driver, nav.link(driver, "Open Record", ""));
											util.pause(logger, "5");
											
											
											util.scrollByVisibleElement(driver, logger, nav.policybreachfield);
											util.verifyElementByXpath(logger, nav.policybreachfield);
											util.selectBoxByValue(logger, nav.policybreachfield, "No");
											util.pause(logger, "10");
											
											util.scrollByVisibleElement(driver, logger, nav.reviewstatusfield);
											util.verifyElementByXpath(logger, nav.reviewstatusfield);
											util.selectBoxByValue(logger, nav.reviewstatusfield, "Approved");
											util.pause(logger, "10");

											util.scrollByVisibleElement(driver, logger, nav.button(driver, "Update", ""));
											util.verifyElementByXpath(logger, nav.button(driver, "Update", ""));
											util.clickByJavascriptExecutor(logger, driver, nav.button(driver, "Update", ""));
											util.pause(logger, "10");
											
											util.scrollByVisibleElement(driver, logger, nav.tab_reviewtasksWFH);
											util.verifyElementByXpath(logger, nav.tab_reviewtasksWFH);
											util.clickByJavascriptExecutor(logger, driver, nav.tab_reviewtasksWFH);
											util.pause(logger, "10");
											
											util.clickByJavascriptExecutor(logger, driver, nav.recordAP55);
											util.pause(logger, "5");
											util.waitTillElementIsClickable(logger, driver, nav.link(driver, "Open Record", ""));
											util.clickByJavascriptExecutor(logger, driver, nav.link(driver, "Open Record", ""));
											util.pause(logger, "5");
											

											util.scrollByVisibleElement(driver, logger, nav.tab_Activity);
											util.verifyElementByXpath(logger, nav.tab_Activity);
											util.clickByJavascriptExecutor(logger, driver, nav.tab_Activity);
											util.pause(logger, "5");
											
											util.scrollByVisibleElement(driver, logger, nav.lnk_additionalactions);
											util.verifyElementByXpath(logger, nav.lnk_additionalactions);
											util.clickByJavascriptExecutor(logger, driver, nav.lnk_additionalactions);
											util.pause(logger, "5");
											
											util.scrollByVisibleElement(driver, logger, nav.lnk_reloadform);
											util.verifyElementByXpath(logger, nav.lnk_reloadform);
											util.clickByJavascriptExecutor(logger, driver, nav.lnk_reloadform);
											util.pause(logger, "10");
											
											util.waitTillElementIsVisible(logger, driver, nav.link(driver, "Show email details", ""));
											util.pause(logger, "10");

											
											Actions actions = new Actions(driver);
											actions.contextClick(nav.link(driver, "Show email details", "")).perform();
											clickDownThenEnter();
											frameHelper.switchToChildWindow(logger, driver,frameHelper.getParentWindowHandle(logger, driver) );
											Thread.sleep(15000);
											
											//Verify the Notifications - add a Do Not Reply note.
											util.waitTillElementIsVisible(logger, driver, nav.label(driver, "This is an automated system generated e-mail. Response to this email is not supported.", ""));
											util.checkForContainsText(logger, nav.label(driver, "This is an automated system generated e-mail. Response to this email is not supported.", ""), "This is an automated system generated e-mail. Response to this email is not supported.");
											util.verifyElementByXpath(logger, nav.label(driver, "This is an automated system generated e-mail. Response to this email is not supported.", ""));
											util.pause(logger, "10");
											
											//Verify if the email notification sent to the Mobility Lead.
											util.scrollByVisibleElement(driver, logger, nav.label(driver, "To: reinier.p.abuel", ""));
											util.checkForContainsText(logger, nav.label(driver, "To: reinier.p.abuel", ""), "To: test");
											util.verifyElementByXpath(logger, nav.label(driver, "To: reinier.p.abuel", ""));
											util.pause(logger, "10");
										
										
											}
											catch (Exception e) {
													util.screenShotAndErrorMsg(logger, e, driver, "Unable to verify notifications with Do not reply email content.");

											}
													extent.endTest(logger);
													extent.flush();
													driver.close();
											}
					
	
					public void OpenP68ReviewTask(ExtentTest logger) {
						try {
							util.selectBoxByValue(logger, nav.dropdown(driver, "Search", "Review Tasks"), "Applicable Policy"); util.pause(logger, "10");
							//util.waitTillElementIsClickable(logger, driver, nav.backgroundText(driver, "Search", ""));
							util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", "Review Tasks"), "AP68 XBC"); util.pause(logger, "5");
							
							//Added code for mouse hover to the preview button - hermaine.c.t.canania
							WebElement preview = driver.findElement(By.xpath("//*[contains(@aria-label,'Preview')]/parent::td//a[@data-list_id='x_amspi_policy_request_task.x_amspi_policy_req_review_task_v2.u_task_number']"));

							//Creating object of an Actions class
							Actions action = new Actions(driver);

							//Performing the mouse hover action on the target element.
							action.moveToElement(preview).perform();
							
							util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Preview", "", "Review Tasks")); util.pause(logger, "5");
							util.clickOn(logger, nav.button(driver, "Open Record", ""));
							 util.pause(logger, "5");
						}
						catch (Exception e) {
							util.screenShotAndErrorMsg(logger, e, driver, "Unable to create Opportunity request");
						}
						extent.endTest(logger);
						extent.flush();
							
						}
					public void OpenP55ReviewTask(ExtentTest logger) {
						try {
							util.selectBoxByValue(logger, nav.dropdown(driver, "Search", "Review Tasks"), "Applicable Policy"); util.pause(logger, "10");
							util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", "Review Tasks"), "AP55"); util.pause(logger, "5");
							
							//Added code for mouse hover to the preview button - hermaine.c.t.canania
							WebElement preview = driver.findElement(By.xpath("//*[contains(@aria-label,'Preview')]/parent::td//a[@data-list_id='x_amspi_policy_request_task.x_amspi_policy_req_review_task_v2.u_task_number']"));

							//Creating object of an Actions class
							Actions action = new Actions(driver);

							//Performing the mouse hover action on the target element.
							action.moveToElement(preview).perform();
							
							util.clickByJavascriptExecutor(logger, driver, nav.tooltip(driver, "Preview", "", "Review Tasks")); util.pause(logger, "5");
							util.clickOn(logger, nav.button(driver, "Open Record", ""));
							 util.pause(logger, "5");
						}
						catch (Exception e) {
							util.screenShotAndErrorMsg(logger, e, driver, "Unable to create Opportunity request");
						}
						extent.endTest(logger);
						extent.flush();
					}
					
					public void VerifyEmailbodytoTravelerEditedTravelDates(ExtentTest logger, String traveler, String requestid, String countryloc, String clientname, String traveldates) {
						try {
							util.scrollByVisibleElement(driver, logger, nav.text(driver, "Body", ""));
							util.checkForContainsText(logger, nav.text(driver, "Body", ""), "To: "+traveler);
						}
						catch (Exception e) {
							util.screenShotAndErrorMsg(logger, e, driver, "Unable to create Opportunity request");
						}
						extent.endTest(logger);
						extent.flush();
					}
					
					public void VerifyEmailbodytoTravelers(ExtentTest logger, String traveler, String requestid, String countryloc, String clientname, String traveldates) {
						try {
							util.scrollByVisibleElement(driver, logger, nav.text(driver, "Body", ""));
							util.checkForContainsText(logger, nav.text(driver, "Body", ""), "To: "+traveler);
							
						}
						catch (Exception e) {
							util.screenShotAndErrorMsg(logger, e, driver, "Unable to create Opportunity request");
						}
						extent.endTest(logger);
						extent.flush();
					}
					
}
