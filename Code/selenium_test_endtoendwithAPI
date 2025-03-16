package com.serviceNow.testcases;

import java.io.IOException;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Calendar;
import java.util.Collections;
import java.util.List;
import java.util.Locale.Category;
import java.util.Map;

import javax.xml.transform.Source;

import java.util.Date;
import java.util.HashMap;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.Parameters;
import org.testng.annotations.Test;

import com.relevantcodes.extentreports.ExtentTest;
import com.relevantcodes.extentreports.LogStatus;

import io.restassured.RestAssured;
import io.restassured.path.json.JsonPath;
import io.restassured.response.Response;
import static io.restassured.RestAssured.*;
import java.awt.AWTException;
import java.text.SimpleDateFormat;
import java.time.Duration;
import io.restassured.RestAssured;
import io.restassured.response.Response;
import io.restassured.http.ContentType;
import java.util.Base64;
import org.openqa.selenium.Alert;

public class CMS_GCP_Test extends CMS_PassportTest {

	public CMS_GCP_Test() throws IOException {
		super();
		// TODO Auto-generated constructor stub
	}
	public String baseURI;
	public String ResourceURI;
	public String ClientID;
	public String ClientSecret;
	public String GrantType;
	public String Scope;
	public String TokenEndPointURL;
	public String ContentTypeJSON;
	public String AuthContentType;
	public String AuthorizationToken;
	public String token = null;
	public String gettoken = null;
	public String DocumentID;
	public String ProcessType;
	public String EnterpriseID;
	public String EmployeeHostCountry;
	public String EmployeeHostState;
	public String EmployeeHostCity;
	public String WorkLocationAddress;
	public String ClientName;
	public String AssignmentStartDate;
	public String FinalGCPEndDttm;
	public String ProjectName;
	public String ProjectAccentureLeader;
	public String TravelApprover;
	public String ChargeCode;
	public String ProposedVisaType;
	public String FrontEndURL;

	public String Payload;
	public String Sys_ID_of_GCP_TP;
	public String HRCaseNumber_PMG_GCP_Restaffing_Modified_Restaffing_or_Intra_Client_Movement_Number;
	public String AssignmentGroup;
	public String TestUser;
	public String UnlistedClientName;
	public String ListedUnlistedClientName;
	public String HRTaskNumber_Eligibility_Check_for_GCP;
	public String TravelPlanNumber_Eligibility_Check_for_GCP;
	public String Template_Eligibility_Check_for_GCP;
	public String HRCaseNumber_Eligibility_Check_for_GCP;
	public String State_Eligibility_Check_for_GCP;
	public String AssignedTo_Eligibility_Check_for_GCP;
	public String AssignmentGroup_Eligibility_Check_for_GCP;
	public String IsTravelerEligible;
	public String ProjectVisaTypeInEligibilityCheckForGCP;
	public String AssignedTo;
	public boolean isH1BTravelPlanDeleted = false;
	public boolean isH1BTravelPlanCreated = false;
	public String H1BNominatedTravelPlanNumber;
	public String description;
	public String worknotes;
	public String HRTaskAction_EligibilityCheckForGCP;
	public String URL_For_HRTask_EligibilityCheckForGCP;
	public String H1BNominatedTravelPlanName;
	// Sumanth and Kamal
	String arr1[] = { ProcessType, EnterpriseID, EmployeeHostCountry, EmployeeHostState, EmployeeHostCity,
			WorkLocationAddress, ClientName, AssignmentStartDate, FinalGCPEndDttm, ProjectName, ProjectAccentureLeader,
			TravelApprover, ChargeCode, ProposedVisaType };

	public static JsonPath rawToJSON(String response) {
		JsonPath js = new JsonPath(response);
		return js;
	}

	public String toMailID;
	public String CcMailID;
	public String fromMailID;
	public String subject;
	public String emailCont;
	public boolean isClientName;
	public String TravelPlanStatus, TravelPlanStage, TravelPlanState;
	public String ActionButton;
	public String Citizenshipusedfortravel;
	public String DestinationReceivingCity;

	public String TP1 = "";
	public String TP2 = "";

	public String PMGCity;
	public String PMGName;
	public String PMGCountry;
	public String PMGStateAbbreviation;
	public String PMGState;
	public String PMGActive;
	public String GCPCity;
	public String Market_Unit_US;
	public String HistoricPMGCity;
	public String HistoricPMGName;
	public String HistoricPMGCountry;
	public String HistoricPMGStateAbbreviation;
	public String HistoricPMGState;
	public String HistoricPMGActive;
	public String HistoricGCPCity;
	public String Historic_Market_Unit_US;
	public String restAPI;
	public String statusValue;
	public String stageValue;


	// To get the data from the GCP excel sheet
	@Parameters("scenarioName")
	@Test
	public void initiateGCPData(String scenarioName) {
		baseURI = getInputData(scenarioName, "BaseURI");
		ResourceURI = getInputData(scenarioName, "ResourceURI");
		ClientID = getInputData("navigate", "ClientID");
		ClientSecret = getInputData("navigate", "ClientSecret");
		GrantType = getInputData("navigate", "GrantType");
		Scope = getInputData("navigate", "Scope");
		TokenEndPointURL = getInputData("navigate", "TokenEndPointURL");
		ContentTypeJSON = getInputData("navigate", "ContentTypeJSON");
		AuthContentType = getInputData("navigate", "AuthContentType");
		ProcessType = getInputData(scenarioName, "ProcessType");
		EnterpriseID = getInputData(scenarioName, "EnterpriseID");
		EmployeeHostCountry = getInputData(scenarioName, "EmployeeHostCountry");
		EmployeeHostState = getInputData(scenarioName, "EmployeeHostState");
		EmployeeHostCity = getInputData(scenarioName, "EmployeeHostCity");
		WorkLocationAddress = getInputData(scenarioName, "WorkLocationAddress");
		ClientName = getInputData(scenarioName, "ClientName");
		AssignmentStartDate = getInputData(scenarioName, "AssignmentStartDate");
		FinalGCPEndDttm = getInputData(scenarioName, "FinalGCPEndDttm");
		ProjectName = getInputData(scenarioName, "ProjectName");
		ProjectAccentureLeader = getInputData(scenarioName, "ProjectAccentureLeader");
		TravelApprover = getInputData(scenarioName, "TravelApprover");
		ChargeCode = getInputData(scenarioName, "ChargeCode");
		ProposedVisaType = getInputData(scenarioName, "ProposedVisaType");
		restAPI = getInputData("navigate", "RESTAPI");

		// REST OF TRAVEL PLAN
		TestName = scenarioName;
		TravelerEID = getInputData(TestName, "TravelerEID");
		Password = getInputData(TestName, "Password");
		TravelerPassword = getInputData(TestName, "Traveler Password");
		ApproverPassword = getInputData("navigate", "Approver Password");
		ApproverEID = getInputData(TestName, "ApproverEID");
		FulfillerEID = getInputData(TestName, "FulfillerEID");
		AdminEID = getInputData(TestName, "AdminEID");
		// URL = getInputData("navigate", "URL") + "/login.do";
		URL = getInputData("navigate", "URL");
		PMGURL = getInputData("navigate", "URL") + "/pmg";
		TravelCheckURL = getInputData("navigate", "URL") + "/travel_check";
		TravelPlansTable = getInputData("navigate", "TravelPlansTable");
		PassportDocumentsTable = getInputData("navigate", "PassportDocumentsTable");
		ADSSNowURL = getInputData("navigate", "ADSSNowURL");
		Immigration_Type = getInputData(TestName, "Immigration Type");
		TravelFrequency = getInputData(TestName, "Travel Frequency");
		policytype = getInputData(TestName, "PolicyType");
		BillingFulfiller = getInputData(TestName, "BillingFulfiller");
		ProjectVisaType = getInputData(TestName, "ProjectVisaType");

		Payload = getInputData(TestName, "Payload");
		UnlistedClientName = getInputData(scenarioName, "UnlistedClientName");
		if (ClientName.isEmpty() == true) {
			isClientName = false;
			ClientName = UnlistedClientName;
		} else {
			isClientName = true;
		}
		System.out.println("Client name? : " + isClientName);

		// GCP HR Task
		AssignedTo_Eligibility_Check_for_GCP = getInputData(TestName, "AssignedTo_Eligibility_Check_for_GCP");
		IsTravelerEligible = getInputData(TestName, "IsTravelerEligible");
		AssignedTo = getInputData(TestName, "AssignedTo");
		ProjectVisaTypeInEligibilityCheckForGCP = getInputData(TestName, "ProjectVisaTypeInEligibilityCheckForGCP");
		worknotes = getInputData(TestName, "WorkNotes");
		description = getInputData(TestName, "Description");
		HRTaskAction_EligibilityCheckForGCP = getInputData(TestName, "HRTaskAction_EligibilityCheckForGCP");

		Citizenshipusedfortravel = getInputData(scenarioName, "Citizenship used for travel");
		DestinationReceivingCity = getInputData(scenarioName, "Destination/Receiving City");

		// GCP 2nd major release
		PMGCity = getInputData(TestName, "PMGCity");
		PMGName = getInputData(TestName, "PMGName");
		PMGCountry = getInputData(TestName, "PMGCountry");
		PMGStateAbbreviation = getInputData(TestName, "PMGStateAbbreviation");
		PMGState = getInputData(TestName, "PMGState");
		PMGActive = getInputData(TestName, "PMGActive");
		GCPCity = getInputData(TestName, "GCPCity");
		if(PMGCountry.contains("USA")) {
			Market_Unit_US = getInputData(TestName, "Market_Unit_US");
		}
		HistoricPMGCity = getInputData(TestName, "PMGCity");
		HistoricPMGName = getInputData(TestName, "PMGName");
		HistoricPMGCountry = getInputData(TestName, "PMGCountry");
		HistoricPMGStateAbbreviation = getInputData(TestName, "PMGStateAbbreviation");
		HistoricPMGState = getInputData(TestName, "PMGState");
		HistoricPMGActive = getInputData(TestName, "PMGActive");
		HistoricGCPCity = getInputData(TestName, "GCPCity");
		if(HistoricPMGCountry.contains("USA")) {
			Historic_Market_Unit_US = getInputData(TestName, "Historic_Market_Unit_US");
		}


	}

	public String callGCP_Payload(String DocumentID) {
		return "[\r\n" + "  {\r\n" + "    \"MessageBody\": {\r\n" + "      \"before\": null,\r\n"
				+ "      \"after\": {\r\n" + "        \"GPT_ID\": 41,        \r\n"
				+ "        \"GPT_MESSAGEJSON\": \"{\\\"DocumentID\\\":" + DocumentID + ",\\\"ProcessType\\\":\\\""
				+ ProcessType + "\\\",\\\"EnterpriseID\\\":\\\"" + EnterpriseID
				+ "\\\",\\\"EmployeeHostCountry\\\":\\\"" + EmployeeHostCountry + "\\\",\\\"EmployeeHostState\\\":\\\""
				+ EmployeeHostState + "\\\",\\\"EmployeeHostCity\\\":\\\"" + EmployeeHostCity
				+ "\\\",\\\"WorkLocationAddress\\\":\\\"" + WorkLocationAddress + "\\\",\\\"ClientName\\\":\\\""
				+ ClientName + "\\\",\\\"AssignmentStartDate\\\":\\\"" + AssignmentStartDate
				+ "\\\",\\\"FinalGCPEndDttm\\\":\\\"" + FinalGCPEndDttm + "\\\",\\\"ProjectName\\\":\\\"" + ProjectName
				+ "\\\",\\\"ProjectAccentureLeader\\\":\\\"" + ProjectAccentureLeader
				+ "\\\",\\\"TravelApprover\\\":\\\"" + TravelApprover + "\\\",\\\"ChargeCode\\\":\\\"" + ChargeCode
				+ "\\\",\\\"ProposedVisaType\\\":\\\"" + ProposedVisaType + "\\\"}\"\r\n" + "      },\r\n"
				+ "      \"source\": {\r\n" + "        \"version\": \"1.9.7.Final\",\r\n"
				+ "        \"connector\": \"sqlserver\",\r\n" + "        \"name\": \"sanitized_source\",\r\n"
				+ "        \"ts_ms\": 1706592600233,\r\n" + "        \"snapshot\": \"false\",\r\n"
				+ "        \"db\": \"sanitized_db\",\r\n" + "        \"sequence\": null,\r\n"
				+ "        \"schema\": \"sanitized_schema\",\r\n" + "        \"table\": \"sanitized_table\",\r\n"
				+ "        \"change_lsn\": \"00006fca:00017778:0007\",\r\n"
				+ "        \"commit_lsn\": \"00006fca:00017778:000c\",\r\n" + "        \"event_serial_no\": 1\r\n"
				+ "      },\r\n" + "      \"op\": \"c\",\r\n" + "      \"ts_ms\": 1706592602330,\r\n"
				+ "      \"transaction\": null\r\n" + "    },\r\n"
				+ "    \"datafabric_topic\": \"sanitized_topic\"\r\n" + "  }\r\n" + "]";
	}

	@Test
	public void getDataFabricAccessTokenForGCP() {
		ExtentTest logger = extent.startTest("accesstoken", "accesstoken");
		try {
			// common method
			// token = getaccesstoken(logger, "access_token");
			String body = "client_id=" + ClientID + "&client_secret=" + ClientSecret + "&grant_type=" + GrantType
					+ "&scope=" + Scope;

			Response responseValue = RestAssured.given().log().all().header("Content-Type", AuthContentType).body(body)
					.get(TokenEndPointURL);
			token = responseValue.then().log().all().extract().path("access_token");
			System.out.println("token" + token);
			logger.log(LogStatus.PASS, "Data fabric token: " + "<b>" + token + "</b> generated");

		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Failed");
			logger.log(LogStatus.FAIL, "Data fabric token failed to generate");
		}
		extent.endTest(logger);

	}

	// unique numeric id for Document ID
	static String generateUniqueDocumentIds(ExtentTest logger) {
		String NumericString = "712345678912358";
		StringBuilder sb = new StringBuilder();
		try {
			for (int i = 0; i < 6; i++) {
				int index = (int) ((NumericString.length() * Math.random() * Math.random() * Math.random()));
				sb.append(NumericString.charAt(index));
			}
		} catch (Exception e) {
			e.printStackTrace();
		}
		System.out.println(sb.toString());
		return sb.toString();
	}

	@Test
	public void PostGCPCall() {
		ExtentTest logger = extent.startTest("PostGCPCall", "Post GCP Call to create Travel plan.");
		try {
			AuthorizationToken = "Bearer " + token;
			DocumentID = generateUniqueDocumentIds(logger);

			RestAssured.baseURI = baseURI;

			String response = given().log().all().header("Authorization", AuthorizationToken)
					.header("Content-Type", ContentTypeJSON).body(callGCP_Payload(DocumentID)).when().post(ResourceURI)
					.then().log().all().extract().response().asString();

			System.out.println(response);

			JsonPath js = rawToJSON(response);
			System.out.println(js.getString("messageResponses[0]"));
			logger.log(LogStatus.INFO, "Result: " + response);
			if (response.contains("Record processed successfully")) {
				logger.log(LogStatus.PASS, "GCP Post api is successfull" + "/n" + response);
			}
		} catch (Exception e) {
			// TODO: handle exception
		}
	}

	@Test
	public void openTravelPlanTable() {
		ExtentTest logger = extent.startTest("Open Travel plan table", "Open Travel plan table.");
		try {
			browserHelper.navigateTo(logger, ADSSNowURL);
			List<String> item = new ArrayList<String>();
			item.add("People Mobility");
			item.add("Travel Plans");
			shadowDomFilterSearch(logger, item.get(0), item, "Travel Plans");
		} catch (Exception e) {
			// TODO: handle exception
		}
	}

	/**
	 * @author k.p.balakrishnan
	 * @implNote : this method is used to save travel plan number by filtering gcp
	 *           document ID
	 */
	@Test
	public void getTravelPlanNumberFromCreatedGCPTravelPlan() {
		ExtentTest logger = extent.startTest("Get travel plan number",
				"get Travel Plan Number From Created GCP Travel Plan.");
		try {
			loginAsAdmin();
			util.pause(logger, "40");
			openTravelPlanTable();
			util.clickOn(logger, portal.label(driver, "All"));
			util.pause(logger, "5");
			addColumn(logger, "GCP Document ID");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Search", ""), "GCP Document ID");
			util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", ""), DocumentID);
			util.pause(logger, "3");
			util.scrollByVisibleElement(driver, logger, nav.link(driver, "Number", ""));
			TravelPlanNumber = nav.getTableCellText(logger, driver, "Number", "");
			System.out.println("TravelPlanNumber: " + TravelPlanNumber);
			logger.log(LogStatus.INFO, TravelPlanNumber);
			util.verifyElementByXpath(logger, nav.tooltip(driver, "Preview TRA", "", ""));
			TravelPlanNumber = nav.tooltip(driver, "Preview TRA", "", "").getAttribute("data-original-title")
					.split(" ")[1].split(":")[0];
			System.out.println("TravelPlanNumber: " + TravelPlanNumber);
			logger.log(LogStatus.INFO, TravelPlanNumber);
			if (TravelPlanNumber.equals(null) || TravelPlanNumber.equals("")) {
				logger.log(LogStatus.FAIL, TravelPlanNumber
						+ "  (Travel plan number) is failed to fetched whose document ID: " + DocumentID);
			} else {
				logger.log(LogStatus.PASS, TravelPlanNumber
						+ " (Travel plan number) is fetched and its associate with document ID: " + DocumentID);
			}
		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL,
					TravelPlanNumber + " (Travel plan number) is failed to fetched whose document ID: " + DocumentID);
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void openCreatedGCP_TravelPlanInFormView() {
		ExtentTest logger = extent.startTest("Open Created GCP Travel Plan In Form View",
				"Open Created GCP Travel Plan In Form View.");
		try {
			util.pause(logger, "3");
			util.clickOn(logger, nav.tooltip(driver, "Preview", "", ""));
			util.pause(logger, "6");
			util.clickOn(logger, nav.link(driver, "Open Record", ""));
			util.pause(logger, "5");
			System.out.println("Record: " + TravelPlanNumber + " is opened");
			logger.log(LogStatus.PASS, "Record: " + TravelPlanNumber + " is opened");
			// Save sys ID:
			String currentURL;
			currentURL = driver.getCurrentUrl();
			String id = currentURL.split("%")[2];
			Sys_ID_of_GCP_TP = id.replace("3D", "");
			logger.log(LogStatus.INFO, "Sys_ID_of_GCP_TP : " + Sys_ID_of_GCP_TP);
			logger.log(LogStatus.PASS, "Record: " + TravelPlanNumber + " is opened");
		} catch (Exception e) {
			// TODO: handle exception
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to open travel plan record " + TravelPlanNumber);
			logger.log(LogStatus.FAIL, "Record: " + TravelPlanNumber + " is failed to be opened");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void TravelerOpenCreatedGCP_TravelPlanIn_PMG_Dashboard() {
		ExtentTest logger = extent.startTest("Traveler Open Created GCP TravelPlanIn PMG Dashboard",
				"Traveler Open Created GCP TravelPlanIn PMG Dashboard.");
		try {
			UserLoginAsTraveler();
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Open"));
			util.pause(logger, "5");
			List<WebElement> PageNumbers = driver
					.findElements(By.xpath("(//div[@class='btn-toolbar pull-left']/ul/li/a[@class='ng-binding'])"));
			for (int i = 3; i <= PageNumbers.size(); i++) {
				List<WebElement> cardContent = driver
						.findElements(By.xpath("//md-card-content/div[@class='row']/div/div/div[2]"));
				ArrayList<String> TravelPlanInCard = new ArrayList<String>();
				for (int j = 0; j < cardContent.size(); j += 1) {
					String CardContentTravelPlan = cardContent.get(j).getText();
					if (CardContentTravelPlan.startsWith("TRA")) {
						TravelPlanInCard.add(CardContentTravelPlan);
					}
				}
				// below for loop just for validation.
				for (int a = 0; a < TravelPlanInCard.size(); a++) {
					System.out.println("Travel plan: " + TravelPlanInCard.get(a));
				}

				int k = 0;
				for (int l = 0; l < TravelPlanInCard.size(); l += 1) {
					k = k + 1;
					String CardContentTravelPlan = TravelPlanInCard.get(l);
					System.out.println(CardContentTravelPlan + " found at " + l);
					if (TestName.equalsIgnoreCase("Create New TP In Restaffing Scenario")) {
						TravelPlanNumber = TP1;
					}
					if (CardContentTravelPlan.equals(TravelPlanNumber)) {
						logger.log(LogStatus.INFO, TravelPlanNumber + " is found in the PMG Dashboard Page");
						System.out.println(TravelPlanNumber + " is found in the PMG Dashboard Page");
						scrollToElementToCenter(
								driver.findElement(By.xpath("(//md-card-footer/div/div/button)[" + k + "]")), driver);
						util.pause(logger, "5");
						util.clickOn(logger,
								driver.findElement(By.xpath("(//md-card-footer/div/div/button)[" + k + "]")));
						logger.log(LogStatus.INFO,
								TravelPlanNumber + " is found in the PMG Dashboard Page and 'View' button is clicked");
						System.out.println(
								TravelPlanNumber + " is found in the PMG Dashboard Page and 'View' button is clicked");
						util.waitForPageToLoadCompletely(logger, driver);
						logger.log(LogStatus.PASS,
								TravelPlanNumber + " is successfully opened by traveler in PMG Dashboard");
						break;
					}
				}
				if (getInputData("navigate", "PMGURL").equals(driver.getCurrentUrl())) {

					scrollToElementToCenter(
							driver.findElement(
									By.xpath("(//span[@class=' pull-left']/ul/li/a[@class='ng-binding'])[" + i + "]")),
							driver);
					util.pause(logger, "2");
					util.clickOn(logger, driver.findElement(
							By.xpath("(//span[@class=' pull-left']/ul/li/a[@class='ng-binding'])[" + i + "]")));
					logger.log(LogStatus.INFO, TravelPlanNumber
							+ " is not found in the PMG Dashboard Page. Hence navigating to next page.");
					System.out.println(TravelPlanNumber
							+ " is not found in the PMG Dashboard Page. Hence navigating to next page.");

				} else {
					break;
				}
			}

		} catch (Exception e) {
			// TODO: handle exception
		}
	}

	@Parameters({ "ReuseExistingH1BNominationTravelPlanorNot" })
	@Test
	public void closeCompleteEligibilityCheckForGCPHRTask(String ReuseExistingH1BNominationTravelPlanorNot) {
		ExtentTest logger = extent.startTest("close complete Eligibility Check For GCP HR Task",
				"close completeEligibility Check For GCP HR Task");
		try {
			util.pause(logger, "3");
			//verifyTACValueOnGCPTP();
			
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			util.clickOn(logger, nav.tooltip(driver, "Preview", "", "HR Tasks"));
			util.pause(logger, "11");
			util.clickOn(logger, nav.link(driver, "Open Record", ""));
			util.pause(logger, "5");
			switch (ReuseExistingH1BNominationTravelPlanorNot) {
				case "NoReuseOfExistingH1BNominationTravelPlan":
					util.selectBoxByValue(logger, nav.dropdown(driver, "Is Traveler Eligible", ""), "Yes");
					//util.selectBoxByValue(logger, nav.dropdown(driver, "Project Visa Type", ""), getInputData(TestName, "validVisaType"));
					util.selectBoxByValue(logger, nav.dropdown(driver, "Project Visa Type", ""), ProjectVisaType);
					util.clickOn(logger, nav.button(driver, "Close Complete", ""));
					util.pause(logger, "5");
					verifyStatusAndStageOfTravelPlan("Travel Request", "Awaiting Traveler Information");
					break;
				case "ReuseOfExistingH1BNominationTravelPlan":
					util.selectBoxByValue(logger, nav.dropdown(driver, "Is Traveler Eligible", ""), "No");
					Select select = new Select(nav.dropdown(driver, "Is Traveler Eligible", ""));
					select.selectByIndex(1);
					util.clickOn(logger, nav.button(driver, "Close Complete", ""));
					util.pause(logger, "5");
					break;
				case "AutoCancellationOfIneligibleTP":
					util.selectBoxByValue(logger, nav.dropdown(driver, "Is Traveler Eligible", ""), "No");
					util.clickOn(logger, nav.button(driver, "Close Complete", ""));
					util.pause(logger, "5");
					break;
				case "NonH1BFlow":
					util.selectBoxByValue(logger, nav.dropdown(driver, "Is Traveler Eligible", ""), "Yes");
					util.selectBoxByValue(logger, portal.dropdown(driver, "Project Visa Type"), ProjectVisaType);
					util.clickOn(logger, nav.button(driver, "Close Complete", ""));
					util.pause(logger, "5");
					verifyStatusAndStageOfTravelPlan("Travel Request", "Awaiting Traveler Information");
					break;
			}
		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL, "Eligibility Check For GCP HR Task is not closed");
		}
	}

	@Parameters({ "status", "stage" })
	@Test
	public void verifyStatusAndStageOfTravelPlan(String status, String stage) {
		ExtentTest logger = extent.startTest("verify Status And Stage Of Travel Plan",
				"verify Status And Stage Of Travel Plan");
		try {

			loginAsAdmin();
			util.pause(logger, "10");
			openTravelPlanTable();
			util.clickOn(logger, portal.label(driver, "All"));
			util.selectBoxByValue(logger, nav.dropdown(driver, "Search", ""), "GCP Document ID");
			util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", ""), DocumentID);
			util.pause(logger, "3");
			util.scrollByVisibleElement(driver, logger, nav.link(driver, "Number", ""));
			util.pause(logger, "3");
			util.clickOn(logger, nav.tooltip(driver, "Preview", "", ""));
			util.pause(logger, "6");
			util.clickOn(logger, nav.link(driver, "Open Record", ""));
			util.pause(logger, "5");
			System.out.println("Record: " + TravelPlanNumber + " is opened");
			logger.log(LogStatus.PASS, "Record: " + TravelPlanNumber + " is opened");


			statusValue = util.getSelectedValueFromDropdown(logger, nav.dropdown(driver, "Status", ""));
			stageValue = util.getSelectedValueFromDropdown(logger, nav.dropdown(driver, "Stage", ""));
			System.out.println(statusValue);
			System.out.println(stageValue);


			if (statusValue.equalsIgnoreCase(status) && stageValue.equalsIgnoreCase(stage)) {
				logger.log(LogStatus.PASS, "Status and Stage of Travel Plan is as expected");
				logger.log(LogStatus.INFO, "Status: " + statusValue + " and Stage: " + stageValue);
			} else {
				logger.log(LogStatus.INFO, "Status and Stage of Travel Plan is not as expected");
				logger.log(LogStatus.INFO, "Status: " + statusValue + " and Stage: " + stageValue);
			}
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Failed");
			logger.log(LogStatus.FAIL, "status and stage is not verified");
		}
		extent.endTest(logger);
	}

	@Test
	public void completeAllRPs() {
		ExtentTest logger = extent.startTest("Complete All RPs", "Complete All RPs");
		try {
			// To complete Data Privacy Agreement RP
		if (isDisplayed("//*[contains(text(),'Data Privacy Agreement')]")) {
				DataPrivacyAgreementRP();
			}

			if (getInputData(TestName, "verifyRPs").equalsIgnoreCase("Yes")) {
				String ListOfRPs = getInputData(TestName, "ListOfRPs");
				String[] RPsToBeVerified = ListOfRPs.split(",");
				for (String RP : RPsToBeVerified) {
					if (isDisplayed("//*[contains(text(),'" + RP + "')]")) {
						logger.log(LogStatus.INFO, RP + " is displayed");
					} else {
						logger.log(LogStatus.INFO, RP + " is not displayed");
						break;
					}
				}
			}

			// To complete Confirm Travel Policy RP
			if (isDisplayed("//*[contains(text(),'Confirm Travel Policy')]")) {
				ConfirmTravelPolicyRP();
			}

			// To complete Upload Passport or National Id RP
			if (isDisplayed("//*[contains(text(),'Upload Passport or National Id')]")) {
				CompleteUploadPassportorNationalIdRP();
			}

			// To complete Upload Passport RP
			else if (isDisplayed("//*[contains(text(),'Upload Passport')]")) {
				CompleteUploadPassportRP();
			}

			// To complete Upload Country Specific Document RP
			if (isDisplayed("//*[contains(text(),'Upload Country Specific Document')]")) {
				CompleteUploadCountrySpecificDocumentRP(logger);
			}

			// To Complete Upload Project Questionnaire RP
			if (isDisplayed("//*[contains(text(),'Upload Project Questionnaire')]")) {
				CompleteUploadProjectQuestionnaireRP(logger);
			}

			// To Complete Upload Traveler Questionnaire RP
			if (isDisplayed("//*[contains(text(),'Upload Traveler Questionnaire')]")) {
				CompleteUploadTravelerQuestionnaireRP(logger);
			}

			// To complete Upload CV or Resume RP
			if (isDisplayed("//*[contains(text(),'Upload CV or Resume')]")) {
				CompleteUploadCVorResumeRP(logger);
			}

			// To complete Upload Traveler Provided Immigration Document RP
			if (isDisplayed("//*[contains(text(),'Upload Traveler Provided Immigration Document')]")) {
				CompleteUploadTravelerProvidedImmigrationDocumentRP(logger);
			}

			// To complete Upload Transcripts and Degrees certificates RP
			if (isDisplayed("//*[contains(text(),'Upload Transcripts and Degrees certificates')]")) {
				UploadTranscriptsandDegreescertificates();
			}

			// To complete Immigration Supporting Documents RP
			if (isDisplayed("//*[contains(text(),'Upload Immigration Supporting Documents')]")) {
				CompleteUploadImmigrationSupportingDocumentsRP(logger);
			}

			// To complete Confirm Dependents Accompanying Me RP
			if (isDisplayed("//*[contains(text(),'Confirm Dependents Accompanying Me')]")) {
				CompleteConfirmDependentsAccompanyingMeRP();
			}

			// To complete Upload AP55 Approval RP
			if (isDisplayed("//*[contains(text(),'Upload AP55 Approval')]")) {
				CompleteUploadAP55ApprovalRP();
			}

			// To complete Upload Birth Certificate RP
			if (isDisplayed("//*[contains(text(),'Upload Birth Certificate')]")) {
				CompleteUploadBirthCertificateRP();
			}
			// To complete Upload Marriage Certificate RP
			if (isDisplayed("//*[contains(text(),'Upload Marriage Certificate')]")) {
				CompleteUploadMarriageCertificateRP();
			}

			// To complete Upload Additional Passport Information RP
			if ((isDisplayed("//*[contains(text(),'Upload Additional Passport Information')]"))) {
				UploadAdditionalPassportInformation(logger);
			}
			// Complete Upload Photo RP();
			if (isDisplayed("//*[contains(text(),'Upload Photo')]")) {
				CompleteUploadPhoto();
			}

			// Complete Upload Dependent Information RP();
			if (isDisplayed("//*[contains(text(),'Upload Dependent Information')]")) {
				CompleteUploadDependentInformationRP();
			}

			// Rayees
			// To complete Upload Job Description RP
			if ((isDisplayed("//*[contains(text(),'Upload Job Description')]"))) {
				UploadJobDescription(logger);
			}

			// To complete Traveler Data Collection RP
			if (isDisplayed("//*[contains(text(),'Traveler Data Collection')]")) {
				GCP = true;
				if(policytype.equalsIgnoreCase("750"))
				{
					CompleteTravelerDataCollectionRPGCP();
				}
				else
				{
				    CompleteTravelerDataCollectionRP();
				}
			}

			logger.log(LogStatus.INFO, "All the RPs are closed");
			FrontEndURL = driver.getCurrentUrl();

		} catch (Exception e) {
			// TODO: handle exception
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to Complete All RPs");
			logger.log(LogStatus.FAIL, "Unable to Complete All RPs");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Parameters({ "CloseOrCancel" })
	@Test
	public void closeOrCancelTravelPlan(String closeOrCancel) {
		ExtentTest logger = extent.startTest("Close Or Cancel Travel Plan", "Close Or Cancel Travel Plan");
		try {

			loginAsAdmin();
			OpenTravelPlan();
			util.pause(logger, "10");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Status", ""), closeOrCancel);
			util.clickOn(logger, portal.button(driver, "Save"));
			util.waitForPageToLoadCompletely(logger, driver);
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Failed");
			logger.log(LogStatus.FAIL, "status and stage is not verified");
		}
		extent.endTest(logger);
	}

	@Parameters("Payload")
	@Test
	public void PostGCPCallUsingExistingDocId(String Payload) {
		ExtentTest logger = extent.startTest("PostGCPCall", "Post GCP Call Using Existing Doc Id");
		try {
			AuthorizationToken = "Bearer " + token;
			RestAssured.baseURI = baseURI;
			String response = given().log().all().header("Authorization", AuthorizationToken)
					.header("Content-Type", ContentTypeJSON).body(callGCP_Payload(Payload, DocumentID)).when()
					.post(ResourceURI).then().log().all().extract().response().asString();

			System.out.println(response);
			JsonPath js = rawToJSON(response);
			System.out.println(js.getString("messageResponses[0]"));
			logger.log(LogStatus.INFO, "Result: " + response);
			if (response.contains("Record processed successfully")) {
				logger.log(LogStatus.PASS, "GCP Post api is successfull" + "/n" + response);
			}
		} catch (Exception e) {
			// TODO: handle exception
		}
	}

	public String callGCP_Payload(String colName, String DocumentID) throws InterruptedException {
		Thread.sleep(2);
		String payloadValues = getInputData(TestName, colName);
		String arr[] = payloadValues.split(",");
		// String arr1[] =
		// {ProcessType,EnterpriseID,EmployeeHostCountry,EmployeeHostState,
		// EmployeeHostCity, WorkLocationAddress, ClientName,
		// AssignmentStartDate,FinalGCPEndDttm,ProjectName,ProjectAccentureLeader,TravelApprover,ChargeCode,ProposedVisaType};
		for (int i = 0; i < arr.length; i++) {
			arr1[i] = arr[i];

		}
		Thread.sleep(5);
		System.out.println(arr1[0]);
		System.out.println(arr1[1]);
		return "[\r\n" + "  {\r\n" + "    \"MessageBody\": {\r\n" + "      \"before\": null,\r\n"
				+ "      \"after\": {\r\n" + "        \"GPT_ID\": 41,        \r\n"
				+ "        \"GPT_MESSAGEJSON\": \"{\\\"DocumentID\\\":" + DocumentID + ",\\\"ProcessType\\\":\\\""
				+ ProcessType + "\\\",\\\"EnterpriseID\\\":\\\"" + EnterpriseID
				+ "\\\",\\\"EmployeeHostCountry\\\":\\\"" + EmployeeHostCountry + "\\\",\\\"EmployeeHostState\\\":\\\""
				+ EmployeeHostState + "\\\",\\\"EmployeeHostCity\\\":\\\"" + EmployeeHostCity
				+ "\\\",\\\"WorkLocationAddress\\\":\\\"" + WorkLocationAddress + "\\\",\\\"ClientName\\\":\\\""
				+ ClientName + "\\\",\\\"AssignmentStartDate\\\":\\\"" + AssignmentStartDate
				+ "\\\",\\\"FinalGCPEndDttm\\\":\\\"" + FinalGCPEndDttm + "\\\",\\\"ProjectName\\\":\\\"" + ProjectName
				+ "\\\",\\\"ProjectAccentureLeader\\\":\\\"" + ProjectAccentureLeader
				+ "\\\",\\\"TravelApprover\\\":\\\"" + TravelApprover + "\\\",\\\"ChargeCode\\\":\\\"" + ChargeCode
				+ "\\\",\\\"ProposedVisaType\\\":\\\"" + ProposedVisaType + "\\\"}\"\r\n" + "      },\r\n"
				+ "      \"source\": {\r\n" + "        \"version\": \"1.9.7.Final\",\r\n"
				+ "        \"connector\": \"sqlserver\",\r\n" + "        \"name\": \"sanitized_source\",\r\n"
				+ "        \"ts_ms\": 1706592600233,\r\n" + "        \"snapshot\": \"false\",\r\n"
				+ "        \"db\": \"sanitized_db\",\r\n" + "        \"sequence\": null,\r\n"
				+ "        \"schema\": \"sanitized_schema\",\r\n" + "        \"table\": \"sanitized_table\",\r\n"
				+ "        \"change_lsn\": \"00006fca:00017778:0007\",\r\n"
				+ "        \"commit_lsn\": \"00006fca:00017778:000c\",\r\n" + "        \"event_serial_no\": 1\r\n"
				+ "      },\r\n" + "      \"op\": \"c\",\r\n" + "      \"ts_ms\": 1706592602330,\r\n"
				+ "      \"transaction\": null\r\n" + "    },\r\n"
				+ "    \"datafabric_topic\": \"sanitized_topic\"\r\n" + "  }\r\n" + "]";

	}

	@Test
	public void verifyIfTravelPlanIsReopened() {
		ExtentTest logger = extent.startTest("verify If Travel Plan is Opened", "verify If Travel Plan is Opened");
		try {
			
			loginAsAdmin();
			OpenTravelPlan();
			verifyStatusAndStageOfTravelPlan("Confirmed", "-- None --");
			util.clickOn(logger, portal.label(driver, "Calculations"));
			util.scrollByVisibleElement(driver, logger, portal.text(driver, "Last RP Completed"));
			Select s = new Select(nav.dropdown(driver, "State", ""));
			if (s.getFirstSelectedOption().getText().equalsIgnoreCase("Open")) {
				logger.log(LogStatus.PASS, "Travel Plan is reopened");
			}
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Activities"));
			util.clickOn(logger, portal.label(driver, "Activities"));
			String[] arr = { "Stage", "State", "Status" };
			for (String str : arr) {
				util.verifyElementByXpath(logger, driver.findElement(By.xpath(
						"//li[contains(@class,'h-card_comments')]/following::div/ul/li/span[text()='" + str + "']")),
						str + " is displayed");
				util.verifyElementByXpath(logger,
						driver.findElement(
								By.xpath("//li[contains(@class,'h-card_comments')]/following::div/ul/li/span[text()='"
										+ str + "']/following-sibling::span")),
						str + " change is displayed in Activities tab");
			}
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Failed");
			logger.log(LogStatus.FAIL, "status and stage is not verified");
		}
		extent.endTest(logger);
	}

	@Parameters({ "PMGGCPReinstatement" })
	@Test
	public void verifyHRTaskGenerationAndCloseCompletion(String PMGGCPReinstatement) {
		ExtentTest logger = extent.startTest("verify HR Task Generation And Close Completion",
				"verify HR Task Generation And Close Completion");
		try {
			util.pause(logger, "3");
			loginAsAdmin();
			OpenTravelPlan();

			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, PMGGCPReinstatement, "Short description", "HR Tasks", "Work in Progress");
			util.pause(logger, "5");
			util.clickOn(logger, nav.button(driver, "Close Complete", ""));
			util.pause(logger, "5");
		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL, "Eligibility Check For GCP HR Task is not closed");
		}
	}

	@Test
	public void verifyIfTP2IsCreatedAndControlIsShiftedToTP2() {
		ExtentTest logger = extent.startTest("verify If Travel Plan 2 Is Created", "verify If Travel Plan 2 Is Created");
		try {

			TP2 = util.getElementValue(logger, driver.findElement(By.xpath("//*[text()='Number']/../parent::div/following-sibling::div//input[contains(@style,';')]")));
			System.out.println("Travel Plan 2: " + TP2);
			if (TP2 != TravelPlanNumber) {
				logger.log(LogStatus.PASS, "TP2 is created: " + TP2);
			} else {
				logger.log(LogStatus.FAIL, "TP2 is not created");
			}
			
			verifyStatusAndStageOfTravelPlan("Travel Request", "Awaiting Traveler Information");
			util.clickOn(logger, portal.label(driver, "Main Details"));
			String docid = portal.text(driver, "GCP Document ID").getAttribute("value");
			scrollToElementToCenter(portal.label(driver, "Travel Start Date"), driver);
			String TravelStartDate2 = portal.text(driver, "Travel Start Date").getAttribute("value");
			System.out.println(TravelStartDate2);
			if (docid.contains(DocumentID)) {
				logger.log(LogStatus.PASS, "Document ID is copied to TP2 " + docid);
			}

			OpenTravelPlan(TP1);
			util.clickOn(logger, portal.label(driver, "Main Details"));
			String docid1 = portal.text(driver, "GCP Document ID").getAttribute("value");
			scrollToElementToCenter(portal.label(driver, "Travel End Date"), driver);
			String TravelEndDate1 = portal.text(driver, "Travel End Date").getAttribute("value");
			System.out.println(TravelEndDate1);
			if (docid1.contains("")) {
				logger.log(LogStatus.PASS, "Document ID is deleted from TP1 ");
			}
			SimpleDateFormat sdf = new SimpleDateFormat("dd-MM-yyyy");
			Date d1 = sdf.parse(TravelStartDate2);
			Date d2 = sdf.parse(TravelEndDate1);
			long difference_In_Time = d1.getTime() - d2.getTime();
			float daysBetween = (difference_In_Time / (1000 * 60 * 60 * 24)) / 365;
			if (daysBetween == 1) {
				logger.log(LogStatus.PASS, "End Date of TP1 is updated to TP2 Start Date - 1 ");
			}
			scrollToElementToCenter(portal.label(driver, "Activities"), driver);
			util.clickOn(logger, portal.label(driver, "Activities"));
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "TP2 is not created");
		}
	}

	/**
	 * @author k.p.balakrishnan
	 * 
	 */
	@Test()
	public void TravelerOpenCreatedGCP_TravelPlanIn_PMG_Dashboard_Via_SysID() {
		ExtentTest logger = extent.startTest("Traveler Open Created GCP TravelPlanIn PMG Dashboard via sys ID",
				"Traveler Open Created GCP TravelPlanIn PMG Dashboard via sys ID.");
		try {
			UserLoginAsTraveler();
			StringBuilder TravelPlanURL = new StringBuilder("");
			TravelPlanURL.append(PMGURL).append("/pmg?id=pmg_travel_plan&travel_plan_id=").append(Sys_ID_of_GCP_TP);
			String TravelPlanURLForDashboard = TravelPlanURL.toString();
			browserHelper.navigateTo(logger, TravelPlanURLForDashboard);
			util.waitForPageToLoadCompletely(logger, driver);
			util.pause(logger, "10");
			logger.log(LogStatus.PASS, "Traveler success fully naviagted to Travel plan : " + TravelPlanNumber
					+ "via sys id: " + Sys_ID_of_GCP_TP);
			screenShotAndInfoMsg(logger, driver, "Travel Plan Frontend view");
		} catch (Exception e) {
			logger.log(LogStatus.FAIL,
					"Test method failed: TravelerOpenCreatedGCP_TravelPlanIn_PMG_Dashboard_Via_SysID");
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test method failed: TravelerOpenCreatedGCP_TravelPlanIn_PMG_Dashboard_Via_SysID");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void TravelerCancelsGCPTravelPlan() {
		ExtentTest logger = extent.startTest("Traveler Cancels GCP Travel Plan",
				"Traveler Cancels GCP Travel Plan in PMG Dashboard");
		try {

			util.pause(logger, "3");
			util.verifyElementByXpath(logger, portal.button(driver, "Cancel travel plan"));

			// Click "Cancel This Request" button.
			util.clickOn(logger, findButtonElement(logger, "Cancel travel plan"));
			util.pause(logger, "3");
			util.clickOn(logger, findButtonElement(logger, "Cancel request"));
			util.pause(logger, "3");
			logger.log(LogStatus.PASS, "Traveler Cancels GCP Travel Plan in PMG Dashboard");
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Traveler Unable to Cancels GCP Travel Plan in PMG Dashboard");
			util.screenShotAndErrorMsg(logger, e, driver, "Test method failed: TravelerCancelsGCPTravelPlan");
		}
		extent.endTest(logger);
		extent.flush();

	}

	@Test
	public void VerifyGCPTravelPlanCancelled() {
		ExtentTest logger = extent.startTest("Verify GCP Travel Plan Cancelled",
				"Verify GCP Travel Plan Cancelled in the backend if the travel plan.");
		try {
			TestUser = getInputData(TestName, "TestUser");
			if (TestUser.contains("PMG ADMIN")) {
				loginAsAdmin();
				navigateToNavPageFromPortal();
			} else if (TestUser.contains("PMG FULFILLER")) {
				UserLoginAsFulfiller();
				navigateToNavPageFromPortal();
			} else {
				logger.log(LogStatus.INFO,
						"USER IS ENTERED AS " + TestUser + "./nuser has to be either PMG ADMIN OR PMG FULFILLER");
				logger.log(LogStatus.FAIL, "Login failed");
			}
			OpenTravelPlan();
			// Validate:
			// 1. Status
			TravelPlanStatus = util.getSelectedValueFromDropdown(logger, nav.dropdown(driver, "Status", ""));
			if (TravelPlanStatus.equals("Cancelled")) {
				logger.log(LogStatus.PASS, "Travel Plan Status is " + TravelPlanStatus);
			} else {
				logger.log(LogStatus.FAIL,
						"Travel Plan Status is " + TravelPlanStatus + "./n Travel Plan Status should be Cancelled.");
			}
			// 2. Stage
			TravelPlanStage = util.getSelectedValueFromDropdown(logger, nav.dropdown(driver, "Stage", ""));
			if (TravelPlanStage.equals("Travel Request Cancelled")) {
				logger.log(LogStatus.PASS, "Travel Plan Stage is " + TravelPlanStage);
			} else {
				logger.log(LogStatus.FAIL, "Travel Plan Stage is " + TravelPlanStage
						+ "./n Travel Plan Stage should be Travel Request Cancelled.");
			}
			// 3. state
			util.clickOn(logger, nav.tabName(driver, "Calculations"));
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "State", "Calculations"));
			TravelPlanState = util.getSelectedValueFromDropdown(logger, nav.dropdown(driver, "State", "Calculations"));
			if (TravelPlanState.equals("Closed")) {
				logger.log(LogStatus.PASS, "Travel Plan State is " + TravelPlanState);
			} else {
				logger.log(LogStatus.FAIL,
						"Travel Plan State is " + TravelPlanState + "./n Travel Plan StaTe should be Closed.");
			}
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Test method failed ==> VerifyGCPTravelPlanCancelled");
			util.screenShotAndErrorMsg(logger, e, driver, "Test method failed ==> VerifyGCPTravelPlanCancelled");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Parameters({ "overrideTestName" })
	@Test
	public void validateUpdationsConditionsInGCPTravelPlan(String overrideTestName) {
		ExtentTest logger = extent.startTest("Validate Updations In GCP Travel Plan",
				"Validate Updations In GCP Travel Plan.");
		try {
			// I. Validate conditions
			String fields[] = { "Source", "State", "Started From", "Process Type" };
			String sourceValues[] = { "SourceValueInTravelPlan", "StateValueInTravelPlan",
					"StartedFromValueInTravelPlan", "ProcessTypeValueInTravelPlan", "GCPDocumentIDinTravelPlan" };
			for (String str : fields) {
				addColumn(logger, str);
				util.scrollByVisibleElement(driver, logger, nav.link(driver, str, ""));
				for (String st : sourceValues) {
					st = nav.getTableCellText(logger, driver, str, "");
				}
			}
			boolean ConditionInDocumentID = false;
			boolean ConditionInSource = false;
			boolean ConditionInState = false;
			boolean ConditionInStartedFrom = false;
			boolean ConditionInProcessType = false;
			// 1. Document IDb
			if (DocumentID.equals(sourceValues[4])) {
				logger.log(LogStatus.PASS,
						"GCP Documet ID: " + DocumentID + " is existing in Travel Plan: " + TravelPlanNumber);
				ConditionInDocumentID = true;
			} else {
				logger.log(LogStatus.INFO, "GCP Documet ID: " + DocumentID
						+ " is not existing/not found/ indifferent in Travel Plan: " + TravelPlanNumber);
			}

			// 2. Source
			if (sourceValues[1].equalsIgnoreCase("TRIPP")) {
				ConditionInSource = true;
				logger.log(LogStatus.PASS, "Source Value In Travel Plan: " + sourceValues[1]);
			} else {
				logger.log(LogStatus.INFO, "Source Value In Travel Plan: " + sourceValues[1]);
			}
			if (sourceValues[2].equalsIgnoreCase("Pending") || sourceValues[2].equalsIgnoreCase("Open")
					|| sourceValues[2].equalsIgnoreCase("-- None --")
					|| sourceValues[2].equalsIgnoreCase("Additional Information Requested")) {
				ConditionInSource = true;
				logger.log(LogStatus.PASS, "Source Value In Travel Plan: " + sourceValues[2]);
			} else {
				logger.log(LogStatus.INFO, "Source Value In Travel Plan: " + sourceValues[2]);
			}

			// 4. StartedFrom
			if (sourceValues[3].equals("GCP Hub")) {
				ConditionInStartedFrom = true;
				logger.log(LogStatus.PASS, "Started From Value In Travel Plan is: " + sourceValues[3]);
			} else {
				logger.log(LogStatus.INFO, "Started From Value In Travel Plan is: " + sourceValues[3]);
			}

			// 5. ProcessTypeValueInTravelPlan
			if (sourceValues[4].equals("Fresh Travel") || sourceValues[4].equals("Fresh Travel - Updated")
					|| sourceValues[4].equals("Fresh Travel - Reactivated") || sourceValues[4].equals("Repatriation")
					|| sourceValues[4].equals("Resignation") || sourceValues[4].equals("Localization")
					|| sourceValues[4].equals("Repatriation cancelled")
					|| sourceValues[4].equals("Resignation cancelled")
					|| sourceValues[4].equals("Localization cancelled")
					|| sourceValues[4].equals("Intra Client Movement Modified")
					|| sourceValues[4].equals("Repatriation Modified") || sourceValues[4].equals("Resignation Modified")
					|| sourceValues[4].equals("Localization Modified") || sourceValues[4].equals("PM/ MD Modified")
					|| sourceValues[4].equals("GCP Extension")) {
				ConditionInStartedFrom = true;
				logger.log(LogStatus.PASS, "Started From Value In Travel Plan is: " + sourceValues[4]);
			} else {
				logger.log(LogStatus.INFO, "Started From Value In Travel Plan is: " + sourceValues[4]);
			}

			// II. Validate Field updation
			if (ConditionInProcessType == true && ConditionInStartedFrom == true && ConditionInState == true
					&& ConditionInState == true && ConditionInSource == true && ConditionInDocumentID == true) {
				logger.log(LogStatus.PASS, "Conditions Passed. Hence update can be happened");
				initiateGCPData(overrideTestName);
				logger.log(LogStatus.INFO, "Document ID : " + DocumentID);
				logger.log(LogStatus.INFO, "Travel Plan number : " + TravelPlanNumber);
				PostGCPCall();
				getTravelPlanNumberFromCreatedGCPTravelPlan();
				// 0. Process type
				util.compareTwoStrings(logger, nav.getTableCellText(logger, driver, "Process Type", ""), ProcessType);

				// 14. Destination State/Province/Canton
				addColumn(logger, "Destination State/Province/Canton");
				util.compareTwoStrings(logger,
						nav.getTableCellText(logger, driver, "Destination State/Province/Canton", ""),
						EmployeeHostState);

				openCreatedGCP_TravelPlanInFormView();

				// 1. Traveler User ID
				util.verifyElementByXpath(logger, nav.label(driver, "Traveler User ID", ""));
				util.verifyElementDisabled(logger, nav.text(driver, "Traveler User ID", ""));
				if (EnterpriseID.equals(null)) {
					logger.log(LogStatus.INFO, EnterpriseID + " has no updates.");
					if (util.getElementValue(logger, nav.text(driver, "Traveler User ID", "")).equals(EnterpriseID)) {
						logger.log(LogStatus.PASS, EnterpriseID + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, EnterpriseID + " is affected.");
					}
				} else if (util.getElementValue(logger, nav.text(driver, "Traveler User ID", ""))
						.equals(EnterpriseID)) {
					logger.log(LogStatus.PASS, EnterpriseID + " is updated Successfully.");
				} else {
					logger.log(LogStatus.FAIL,
							"Traveler EID: " + EnterpriseID + " has Invalid data format or updated incorrectly.");
				}

				// 2. Destination Country/Location
				util.verifyElementByXpath(logger, nav.label(driver, "Destination Country/Location", ""));
				util.verifyElementDisabled(logger, nav.text(driver, "Destination Country/Location", ""));
				if (EmployeeHostCountry.equals(null)) {
					logger.log(LogStatus.INFO, EmployeeHostCountry + " has no updates.");
					if (util.getElementValue(logger, nav.text(driver, "Destination Country/Location", ""))
							.equals(EmployeeHostCountry)) {
						logger.log(LogStatus.PASS, EmployeeHostCountry + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, EmployeeHostCountry + " is affected.");
					}
				} else if (util.getElementValue(logger, nav.text(driver, "Destination Country/Location", ""))
						.equals(EmployeeHostCountry)) {
					logger.log(LogStatus.PASS, EmployeeHostCountry + " is updated Successfully.");
				} else {
					logger.log(LogStatus.FAIL, "EmployeeHostCountry: " + EmployeeHostCountry
							+ " has Invalid data format or updated incorrectly.");
				}

				util.verifyElementByXpath(logger, nav.tabName(driver, "Main Details"));
				util.clickOn(logger, nav.tabName(driver, "Main Details"));

				// 3. Project Visa Type
				util.verifyElementByXpath(logger, nav.label(driver, "Project Visa Type", "Main Details"));
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Project Visa Type", "Main Details"));
				util.isEnabled(logger, nav.dropdown(driver, "Project Visa Type", "Main Details"));
				if (ProposedVisaType.equals(null)) {
					logger.log(LogStatus.INFO, ProposedVisaType + " has no updates.");
					if (util.getSelectedValueFromDropdown(logger,
							nav.dropdown(driver, "Project Visa Type", "Main Details")).equals(ProjectVisaType)) {
						logger.log(LogStatus.PASS, ProjectVisaType + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, ProjectVisaType + " is affected.");
					}
				} else if (ProposedVisaType != null) {
					if (util.getSelectedValueFromDropdown(logger,
							nav.dropdown(driver, "Project Visa Type", "Main Details")).equals(ProjectVisaType)) {
						logger.log(LogStatus.PASS, ProjectVisaType + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, ProjectVisaType + " is affected.");
					}
					logger.log(LogStatus.PASS, ProposedVisaType + " is updated Successfully.");
				} else {
					logger.log(LogStatus.FAIL, "ProposedVisaType/ project visa type: " + ProposedVisaType
							+ " has Invalid data format or updated incorrectly.");
				}

				// 4. Travel Start Date
				util.verifyElementByXpath(logger, nav.label(driver, "Travel Start Date", "Main Details"));
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Travel Start Date", "Main Details"));
				if (AssignmentStartDate.equals(null)) {
					logger.log(LogStatus.INFO, AssignmentStartDate + " has no updates.");
					if (util.getElementValue(logger, nav.text(driver, "Travel Start Date", "Main Details"))
							.equals(AssignmentStartDate.split("T")[0])) {
						logger.log(LogStatus.PASS,
								AssignmentStartDate.split("T")[0] + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, AssignmentStartDate.split("T")[0] + " is affected.");
					}
				} else if (util.getElementValue(logger,
						nav.text(driver, "Travel Start Date", "Main Details")) != null) {

					String[] TravelStartDate = AssignmentStartDate.split("T");
					if (util.getElementValue(logger, nav.text(driver, "Travel Start Date", "Main Details"))
							.equals(TravelStartDate[0])) {
						logger.log(LogStatus.PASS, AssignmentStartDate + " is updated Successfully.");
					}

				} else {
					logger.log(LogStatus.FAIL, "AssignmentStartDate: " + AssignmentStartDate + AssignmentStartDate
							+ " has Invalid data format or updated incorrectly.");
				}

				// 5. Travel End Date
				util.verifyElementByXpath(logger, nav.label(driver, "Travel End Date", "Main Details"));
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Travel End Date", "Main Details"));
				if (FinalGCPEndDttm.equals(null)) {
					logger.log(LogStatus.INFO, FinalGCPEndDttm + " has no updates.");
					if (util.getElementValue(logger, nav.text(driver, "Travel End Date", "Main Details"))
							.equals(FinalGCPEndDttm.split("T")[0])) {
						logger.log(LogStatus.PASS,
								FinalGCPEndDttm.split("T")[0] + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, FinalGCPEndDttm.split("T")[0] + " is affected.");
					}
				} else if (util.getElementValue(logger, nav.text(driver, "Travel End Date", "Main Details")) != null) {

					String[] TravelEndDate = FinalGCPEndDttm.split("T");
					if (util.getElementValue(logger, nav.text(driver, "Travel End Date", "Main Details"))
							.equals(TravelEndDate[0])) {
						logger.log(LogStatus.PASS, FinalGCPEndDttm + " is updated Successfully.");
					}

				} else {
					logger.log(LogStatus.FAIL,
							"FinalGCPEndDttm: " + FinalGCPEndDttm + " has Invalid data format or updated incorrectly.");
				}

				// 6. Street Address if not in office
				util.verifyElementByXpath(logger, nav.label(driver, "Street Address if not in office", "Main Details"));
				util.scrollByVisibleElement(driver, logger,
						nav.label(driver, "Street Address if not in office", "Main Details"));
				util.isEnabled(logger, nav.text(driver, "Street Address if not in office", "Main Details"));
				if (WorkLocationAddress.equals(null)) {
					logger.log(LogStatus.INFO, WorkLocationAddress + " has no updates.");
					if (util.getElementValue(logger,
							nav.text(driver, "Street Address if not in office", "Main Details"))
							.equals(WorkLocationAddress)) {
						logger.log(LogStatus.PASS, WorkLocationAddress + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, WorkLocationAddress + " is affected.");
					}
				} else if (util
						.getElementValue(logger, nav.text(driver, "Street Address if not in office", "Main Details"))
						.equals(WorkLocationAddress)) {
					logger.log(LogStatus.PASS, "Street Address if not in office / WorkLocationAddress"
							+ WorkLocationAddress + " is updated Successfully.");
				} else {
					logger.log(LogStatus.FAIL, "Work Location address: " + WorkLocationAddress
							+ " has Invalid data format or updated incorrectly.");
				}

				// 7. Destination Office City
				util.verifyElementByXpath(logger, nav.label(driver, "Destination Office City", "Main Details"));
				util.scrollByVisibleElement(driver, logger,
						nav.label(driver, "Destination Office City", "Main Details"));
				util.isEnabled(logger, nav.text(driver, "Destination Office City", "Main Details"));
				if (EmployeeHostCity.equals(null)) {
					logger.log(LogStatus.INFO, EmployeeHostCity + " has no updates.");
					if (util.getElementValue(logger, nav.text(driver, "Destination Office City", "Main Details"))
							.contains(EmployeeHostCity)) {
						logger.log(LogStatus.PASS, EmployeeHostCity + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, EmployeeHostCity + " is affected.");
					}
				} else if (util.getElementValue(logger, nav.text(driver, "Destination Office City", "Main Details"))
						.contains(EmployeeHostCity)) {
					logger.log(LogStatus.PASS, EmployeeHostCity + " is updated Successfully.");
				} else {
					logger.log(LogStatus.FAIL, "Destination office city : " + EmployeeHostCity
							+ " has Invalid data format or updated incorrectly.");
				}

				// 8. Unlisted Client Name
				boolean UnlistedClientNameUpdTateFlag = false;
				util.verifyElementByXpath(logger, nav.label(driver, "Unlisted Client Name", "Main Details"));
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Unlisted Client Name", "Main Details"));
				util.isEnabled(logger, nav.text(driver, "Unlisted Client Name", "Main Details"));
				if (UnlistedClientName.equals(null) || UnlistedClientName.equals("")) {
					logger.log(LogStatus.INFO, UnlistedClientName + " has no updates.");
					if (util.getElementValue(logger, nav.text(driver, "Unlisted Client Name", "Main Details"))
							.equals(UnlistedClientName)) {
						logger.log(LogStatus.PASS, UnlistedClientName + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, UnlistedClientName + " is affected.");
					}
				} else if (util.getElementValue(logger, nav.text(driver, "Unlisted Client Name", "Main Details"))
						.equals(UnlistedClientName)) {
					UnlistedClientNameUpdTateFlag = true;
					logger.log(LogStatus.PASS, UnlistedClientName + " is updated Successfully.");
				} else {
					logger.log(LogStatus.FAIL, "Unlisted Client Name : " + UnlistedClientName
							+ " has Invalid data format or updated incorrectly.");
				}

				// 9. client name
				util.verifyElementByXpath(logger, nav.label(driver, "Client Name", "Main Details"));
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Client Name", "Main Details"));
				util.isEnabled(logger, nav.text(driver, "Client Name", "Main Details"));
				if (UnlistedClientNameUpdTateFlag = true) {
					logger.log(LogStatus.INFO, "Update is happened for unlisted client name");
					if (util.getElementValue(logger, nav.text(driver, "Client Name", "Main Details"))
							.equals(ClientName)) {
						logger.log(LogStatus.PASS, ClientName + " is not updated and remains same");
					}
				} else if (ClientName.equals(null) || ClientName.equals("")) {
					logger.log(LogStatus.INFO, ClientName + " has no updates.");
					if (util.getElementValue(logger, nav.text(driver, "Client Name", "Main Details"))
							.equals(ClientName)) {
						logger.log(LogStatus.PASS, ClientName + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, ClientName + " is affected.");
					}
				} else if (util.getElementValue(logger, nav.text(driver, "Client Name", "Main Details"))
						.equals(ClientName)) {
					logger.log(LogStatus.PASS, ClientName + " is updated Successfully.");
				} else {
					logger.log(LogStatus.FAIL,
							"Client Name : " + ClientName + " has Invalid data format or updated incorrectly.");
				}

				// 10. Project Name
				util.verifyElementByXpath(logger, nav.label(driver, "Project Name", "Main Details"));
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Project Name", "Main Details"));
				util.isEnabled(logger, nav.text(driver, "Project Name", "Main Details"));
				if (ProjectName.equals(null)) {
					logger.log(LogStatus.INFO, ProjectName + " has no updates.");
					if (util.getElementValue(logger, nav.text(driver, "Project Name", "Main Details"))
							.equals(ProjectName)) {
						logger.log(LogStatus.PASS, ProjectName + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, ProjectName + " is affected.");
					}
				} else if (util.getElementValue(logger, nav.text(driver, "Project Name", "Main Details"))
						.equals(ProjectName)) {
					logger.log(LogStatus.PASS, ProjectName + " is updated Successfully.");
				} else {
					logger.log(LogStatus.FAIL,
							"Project Name : " + ProjectName + " has Invalid data format or updated incorrectly.");
				}

				// 11. Project Accenture Leader
				util.verifyElementByXpath(logger, nav.label(driver, "Project Accenture Leader", "Main Details"));
				util.scrollByVisibleElement(driver, logger,
						nav.label(driver, "Project Accenture Leader", "Main Details"));
				util.isEnabled(logger, nav.text(driver, "Project Accenture Leader", "Main Details"));
				if (ProjectAccentureLeader.equals(null)) {
					logger.log(LogStatus.INFO, ProjectAccentureLeader + " has no updates.");
					if (util.getElementValue(logger, nav.text(driver, "Project Accenture Leader", "Main Details"))
							.equals(ProjectAccentureLeader)) {
						logger.log(LogStatus.PASS,
								ProjectAccentureLeader + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, ProjectAccentureLeader + " is affected.");
					}
				} else if (util.getElementValue(logger, nav.text(driver, "Project Accenture Leader", "Main Details"))
						.equals(ProjectAccentureLeader)) {
					logger.log(LogStatus.PASS, ProjectAccentureLeader + " is updated Successfully.");
				} else {
					logger.log(LogStatus.FAIL, "Project Accenture Leader : " + ProjectAccentureLeader
							+ " has Invalid data format or updated incorrectly.");
				}

				// 12. Travel Approver
				util.verifyElementByXpath(logger, nav.label(driver, "Travel Approver", "Main Details"));
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Travel Approver", "Main Details"));
				util.isEnabled(logger, nav.text(driver, "Travel Approver", "Main Details"));
				if (TravelApprover.equals(null)) {
					logger.log(LogStatus.INFO, TravelApprover + " has no updates.");
					if (util.getElementValue(logger, nav.text(driver, "Travel Approver", "Main Details"))
							.equals(TravelApprover)) {
						logger.log(LogStatus.PASS, TravelApprover + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, TravelApprover + " is affected.");
					}
				} else if (util.getElementValue(logger, nav.text(driver, "Travel Approver", "Main Details"))
						.equals(TravelApprover)) {
					logger.log(LogStatus.PASS, TravelApprover + " is updated Successfully.");
				} else {
					logger.log(LogStatus.FAIL,
							"Travel Approver : " + TravelApprover + " has Invalid data format or updated incorrectly.");
				}

				// 13. Charge Code
				util.verifyElementByXpath(logger, nav.label(driver, "Charge Code", "Main Details"));
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Charge Code", "Main Details"));
				util.isEnabled(logger, nav.text(driver, "Charge Code", "Main Details"));
				if (ChargeCode.equals(null)) {
					logger.log(LogStatus.INFO, ChargeCode + " has no updates.");
					if (util.getElementValue(logger, nav.text(driver, "Charge Code", "Main Details"))
							.equals(ChargeCode)) {
						logger.log(LogStatus.PASS, ChargeCode + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, ChargeCode + " is affected.");
					}
				} else if (ChargeCode != null) {
					if (util.getElementValue(logger, nav.text(driver, "Charge Code", "Main Details"))
							.equals(ChargeCode)) {
						logger.log(LogStatus.PASS, ChargeCode + " is not updated and value is not affected.");
					} else {
						logger.log(LogStatus.FAIL, ChargeCode + " is affected.");
					}
					logger.log(LogStatus.PASS, ChargeCode + " is updated Successfully.");
				} else {
					logger.log(LogStatus.FAIL,
							"Charge Code: " + ChargeCode + " has Invalid data format or updated incorrectly.");
				}

			} else {
				logger.log(LogStatus.INFO, "Conditions failed. Hence update cannot be happened");
				if (getInputData(sourceValues[4], sourceValues[5]).contains("True")) {
					logger.log(LogStatus.FAIL, "Conditions failed. Hence update cannot be happened");
				} else {
					logger.log(LogStatus.PASS, "Conditions failed. Hence update cannot be happened");
				}

			}
		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL, "Test method failed: Validate Updations In GCP Travel Plan");
			util.screenShotAndErrorMsg(logger, e, driver, "Test method failed: Validate Updations In GCP Travel Plan");
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author lakshmi.rm
	 */
	// User Story 431636: Refined - PMG - CMS - GCP - HR Task - GCP Cancellation or
	// On-Hold
	@Test
	public void GCPCancellationOrOnHold_HRTask() {
		ExtentTest logger = extent.startTest("Validate GCP Cancellation or On-Hold HR Task",
				"Validate GCP Cancellation or On-Hold HR Task");
		try {
			
			util.pause(logger, "5");
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, "PMG GCP Cancellation/ On-Hold", "Short description", "HR Tasks", "Work in Progress");
			validateGCPHRTaskFieldMappingAndEditabilityForPayload3(logger, "PMG GCP Cancellation/ On-Hold",
					"PMG GCP Cancellation/ On-Hold", "T39377.01");
			verifyFieldsInActivitiesSection(logger, "Assigned to", "T39377.01");
			verifyFieldsInActivitiesSection(logger, "Work notes", "For Testing.");

			// Button Verification
			util.verifyElementByXpath(logger, nav.button(driver, "Update", ""));
			util.verifyElementByXpath(logger, nav.button(driver, "Close Complete", ""));
			util.clickOn(logger, nav.button(driver, "Close Complete", ""));
			
		} catch (Exception e) {

			// TODO: handle

			logger.log(LogStatus.FAIL, "User failed to Validate GCP Cancellation or On-Hold HR Task");

		}

	}

	// Common method for GCP HR Tasks
	public String Auto_Generated_HR_Task_Number;
	public String Auto_Generated_HR_Case_Number;

	/**
	 * @author lakshmi.rm
	 */
	// User Story 491960: Refined - PMG - CMS - GCP - HR Task - Fresh Travel -
	// Updated, Repatriation, Resignation, Localization, Repatriation/ Resignation/
	// Localization cancelled
	// User Story 411628: Refined - PMG - CMS - GCP - Travel Plan - Fresh Travel -
	// Updated, Repatriation, Resignation, Localization, Repatriation/ Resignation/
	// Localization cancelled - TP update

	@Test
	public void updationOfProcessTypes() {
		ExtentTest logger = extent.startTest("Verify Updation of Process Types", "Verify Updation of Process Types");
		try {

			getTravelPlanNumberFromCreatedGCPTravelPlan();
			openCreatedGCP_TravelPlanInFormView();

			ProcessType = getInputData(TestName, "ProcessType");
			EnterpriseID = getInputData(TestName, "EnterpriseID");
			EmployeeHostCountry = getInputData(TestName, "EmployeeHostCountry");
			EmployeeHostState = getInputData(TestName, "EmployeeHostState");
			EmployeeHostCity = getInputData(TestName, "EmployeeHostCity");
			WorkLocationAddress = getInputData(TestName, "WorkLocationAddress");
			ClientName = getInputData(TestName, "ClientName");
			AssignmentStartDate = getInputData(TestName, "AssignmentStartDate");
			FinalGCPEndDttm = getInputData(TestName, "FinalGCPEndDttm");
			ProjectName = getInputData(TestName, "ProjectName");
			ProjectAccentureLeader = getInputData(TestName, "ProjectAccentureLeader");
			TravelApprover = getInputData(TestName, "TravelApprover");
			ChargeCode = getInputData(TestName, "ChargeCode");
			ProposedVisaType = getInputData(TestName, "ProposedVisaType");

			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Activities"));
			util.clickOn(logger, portal.label(driver, "Activities"));

			String fieldNames[] = { "Process Type", "Traveler User ID", "Destination Country/Location",
					"Destination State/Province/Canton", "Destination Office City",
					"Street Address if not in office", "Client Name", "Travel Start Date",
					"Travel End Date", "Project Name", "Project Accenture Leader", "Travel Approver",
					"Charge Code", "Project Visa Type" };
			String newValues[];
			String existingValues[] = { ProcessType, EnterpriseID, EmployeeHostCountry, EmployeeHostState,
					EmployeeHostCity,
					WorkLocationAddress, ClientName, AssignmentStartDate, FinalGCPEndDttm, ProjectName,
					ProjectAccentureLeader, TravelApprover, ChargeCode, ProposedVisaType };

			for (int j = 1; j <= 13; j++) {
				String payloadValues = getInputData(TestName, "Payload2" + j);
				newValues = payloadValues.split(",");

				System.out.println("------------------------------------------------------------------------");
				System.out.println("Changes for " + newValues[0] + " : ");
				for (int i = 0; i < fieldNames.length; i++) {
					if (fieldNames[i].contains("Charge Code") || (fieldNames[i].contains("Project Visa Type"))
							|| (fieldNames[i].contains("Traveler User ID")
									|| (fieldNames[i].contains("Destination Country/Location")))) {
						System.out.println(fieldNames[i] + " value ");
						System.out.println("Existing value: " + existingValues[i]);
						System.out.println("New value     : " + newValues[i]);
						System.out.println(fieldNames[i] + " changes will not be updated.");
						logger.log(LogStatus.PASS, fieldNames[i] + " changes will not be updated. " + "Existing value: "
								+ existingValues[i] + " New value: " + newValues[i]);
					} else if (newValues[i].equals(existingValues[i])) {
						System.out.println(fieldNames[i] + " has no change in value");
						logger.log(LogStatus.PASS, fieldNames[i] + " has no change in value");
					} else {
						System.out.println(fieldNames[i] + " value is updated");
						System.out.println("Existing value: " + existingValues[i]);
						System.out.println("New value     : " + newValues[i]);
						logger.log(LogStatus.PASS, fieldNames[i] + " value is updated. " + "Existing value: "
								+ existingValues[i] + "New value: " + newValues[i]);
						verifyFieldsInActivitiesTab(logger, fieldNames[i], existingValues[i], newValues[i]);
						existingValues[i] = newValues[i];
					}
				}
			}

			util.pause(logger, "5");
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Search", "HR Tasks"), "Short description");
			util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", "HR Tasks"),
					"Auto-updates from GCP Hub");
			util.clickOn(logger, nav.tooltip(driver, "Preview", "", "HR Tasks"));
			util.pause(logger, "11");
			util.clickOn(logger, nav.link(driver, "Open Record", ""));
			util.pause(logger, "5");
			util.pause(logger, "15");
			ProcessType = "PM/ MD Modified";
			validateGCPHRTaskFieldMappingAndEditability(logger, "Auto-updates from GCP Hub",
					"Auto-updates from GCP Hub", "T39377.01");

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to Verify Updation of Process Types");
			util.screenShotAndErrorMsg(logger, e, driver, "Verify Updation of Process Types");
		}
		extent.endTest(logger);
		extent.flush();
	}


	// Created by: hermaine.c.t.canania
	// Verification of updated existing payload values
	@Test
	public void updateGCPExistingPayload() {
		ExtentTest logger = extent.startTest("Verification of updated existing payload values", "Verification of updated existing payload values");
		try {

			String[] fieldNames = { "Process Type", "Traveler User ID", "Destination Country/Location",
                "Destination State/Province/Canton", "Destination Office City",
                "Street Address if not in office", "Client Name", "Travel Start Date",
                "Travel End Date", "Project Name", "Project Accenture Leader", "Travel Approver",
                "Charge Code", "Project Visa Type" };

        // Fetch existing values using getInputData method
        String ProcessType = getInputData(TestName, "ProcessType");
        String EnterpriseID = getInputData(TestName, "EnterpriseID");
        String EmployeeHostCountry = getInputData(TestName, "EmployeeHostCountry");
        String EmployeeHostState = getInputData(TestName, "EmployeeHostState");
        String EmployeeHostCity = getInputData(TestName, "EmployeeHostCity");
        String WorkLocationAddress = getInputData(TestName, "WorkLocationAddress");
        String ClientName = getInputData(TestName, "ClientName");
        String AssignmentStartDate = getInputData(TestName, "AssignmentStartDate");
        String FinalGCPEndDttm = getInputData(TestName, "FinalGCPEndDttm");
        String ProjectName = getInputData(TestName, "ProjectName");
        String ProjectAccentureLeader = getInputData(TestName, "ProjectAccentureLeader");
        String TravelApprover = getInputData(TestName, "TravelApprover");
        String ChargeCode = getInputData(TestName, "ChargeCode");
        String ProposedVisaType = getInputData(TestName, "ProposedVisaType");

        // Store existing values in a map
        Map<String, String> existingValuesMap = new HashMap<>();
        existingValuesMap.put("Process Type", ProcessType);
        existingValuesMap.put("Traveler User ID", EnterpriseID);
        existingValuesMap.put("Destination Country/Location", EmployeeHostCountry);
        existingValuesMap.put("Destination State/Province/Canton", EmployeeHostState);
        existingValuesMap.put("Destination Office City", EmployeeHostCity);
        existingValuesMap.put("Street Address if not in office", WorkLocationAddress);
        existingValuesMap.put("Client Name", ClientName);
        existingValuesMap.put("Travel Start Date", AssignmentStartDate);
        existingValuesMap.put("Travel End Date", FinalGCPEndDttm);
        existingValuesMap.put("Project Name", ProjectName);
        existingValuesMap.put("Project Accenture Leader", ProjectAccentureLeader);
        existingValuesMap.put("Travel Approver", TravelApprover);
        existingValuesMap.put("Charge Code", ChargeCode);
        existingValuesMap.put("Project Visa Type", ProposedVisaType);

        // Fetch payload values
        String payload = getInputData(TestName, "Payload2");
        if (payload != null && !payload.isEmpty()) {
            String[] newValues = payload.split(",");
            
            System.out.println("Field Name | Existing Value | New Value");
            for (int i = 0; i < fieldNames.length; i++) {
                String fieldName = fieldNames[i];
                String existingValue = existingValuesMap.getOrDefault(fieldName, "N/A");
                String newValue = i < newValues.length ? newValues[i] : "N/A";
                
                // Ensure Project Visa Type retains its existing value
                if (fieldName.equals("Project Visa Type")) {
                    newValue = existingValue;
                }
                
                if (!existingValue.equals(newValue)) {
                    System.out.println(fieldName + " | " + existingValue + " | " + newValue);
                } else {
                    System.out.println(fieldName + " | " + existingValue + " | [No change to the field value]");
                }
            }
        }

			UserLoginAsFulfiller();
			OpenTravelPlan();	
			util.pause(logger, "5");
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, "PMG GCP Restaffing, Modified Restaffing or Intra Client Movement", "Short description", "HR Tasks", "Work in Progress");
			util.pause(logger, "15");
			validateGCPHRTaskFieldMappingAndEditability(logger, "PMG GCP Restaffing, Modified Restaffing or Intra Client Movement",
					"PMG GCP Restaffing, Modified Restaffing or Intra Client Movement", "T39377.01");

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to Verify Updation of Process Types");
			util.screenShotAndErrorMsg(logger, e, driver, "Verify Updation of Process Types");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// Created by: hermaine.c.t.canania
	// Verification of updated existing payload values
	@Test
	public void updateGCPExistingPayloadForReinstatement() {
		ExtentTest logger = extent.startTest("Verification of updated existing payload values", "Verification of updated existing payload values");
		try {

			String[] fieldNames = { "Process Type", "Traveler User ID", "Destination Country/Location",
                "Destination State/Province/Canton", "Destination Office City",
                "Street Address if not in office", "Client Name", "Travel Start Date",
                "Travel End Date", "Project Name", "Project Accenture Leader", "Travel Approver",
                "Charge Code", "Project Visa Type" };

        // Fetch existing values using getInputData method
        String ProcessType = getInputData(TestName, "ProcessType");
        String EnterpriseID = getInputData(TestName, "EnterpriseID");
        String EmployeeHostCountry = getInputData(TestName, "EmployeeHostCountry");
        String EmployeeHostState = getInputData(TestName, "EmployeeHostState");
        String EmployeeHostCity = getInputData(TestName, "EmployeeHostCity");
        String WorkLocationAddress = getInputData(TestName, "WorkLocationAddress");
        String ClientName = getInputData(TestName, "ClientName");
        String AssignmentStartDate = getInputData(TestName, "AssignmentStartDate");
        String FinalGCPEndDttm = getInputData(TestName, "FinalGCPEndDttm");
        String ProjectName = getInputData(TestName, "ProjectName");
        String ProjectAccentureLeader = getInputData(TestName, "ProjectAccentureLeader");
        String TravelApprover = getInputData(TestName, "TravelApprover");
        String ChargeCode = getInputData(TestName, "ChargeCode");
        String ProposedVisaType = getInputData(TestName, "ProposedVisaType");

        // Store existing values in a map
        Map<String, String> existingValuesMap = new HashMap<>();
        existingValuesMap.put("Process Type", ProcessType);
        existingValuesMap.put("Traveler User ID", EnterpriseID);
        existingValuesMap.put("Destination Country/Location", EmployeeHostCountry);
        existingValuesMap.put("Destination State/Province/Canton", EmployeeHostState);
        existingValuesMap.put("Destination Office City", EmployeeHostCity);
        existingValuesMap.put("Street Address if not in office", WorkLocationAddress);
        existingValuesMap.put("Client Name", ClientName);
        existingValuesMap.put("Travel Start Date", AssignmentStartDate);
        existingValuesMap.put("Travel End Date", FinalGCPEndDttm);
        existingValuesMap.put("Project Name", ProjectName);
        existingValuesMap.put("Project Accenture Leader", ProjectAccentureLeader);
        existingValuesMap.put("Travel Approver", TravelApprover);
        existingValuesMap.put("Charge Code", ChargeCode);
        existingValuesMap.put("Project Visa Type", ProposedVisaType);

        // Fetch payload values
        String payload = getInputData(TestName, "Payload2");
        if (payload != null && !payload.isEmpty()) {
            String[] newValues = payload.split(",");
            
            System.out.println("Field Name | Existing Value | New Value");
            for (int i = 0; i < fieldNames.length; i++) {
                String fieldName = fieldNames[i];
                String existingValue = existingValuesMap.getOrDefault(fieldName, "N/A");
                String newValue = i < newValues.length ? newValues[i] : "N/A";
                
                // Ensure Project Visa Type retains its existing value
                if (fieldName.equals("Project Visa Type")) {
                    newValue = existingValue;
                }
                
                if (!existingValue.equals(newValue)) {
                    System.out.println(fieldName + " | " + existingValue + " | " + newValue);
                } else {
                    System.out.println(fieldName + " | " + existingValue + " | [No change to the field value]");
                }
            }
        }

			UserLoginAsFulfiller();
			OpenTravelPlan();	
			util.pause(logger, "5");
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, "PMG GCP Reinstatement", "Short description", "HR Tasks", "Work in Progress");
			util.pause(logger, "15");
			validateGCPHRTaskFieldMappingAndEditability(logger, "PMG GCP Reinstatement",
					"PMG GCP Reinstatement", "T39377.01");

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to Verify Updation of Process Types");
			util.screenShotAndErrorMsg(logger, e, driver, "Verify Updation of Process Types");
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author lakshmi.rm
	 */
	// User Story 661497: Refined - PMG - CMS - GCP - Travel Plan - Handling of
	// 'Client Name' and
	// 'Unlisted Client Name' for multiple updates
	@Test
	public void handlingOfClientNameForMultipleUpdates() {
		ExtentTest logger = extent.startTest("Handling Client Name Updates", "Handling Client Name Updates");
		try {

			util.scrollByVisibleElement(driver, logger, nav.tabName(driver, "Main Details"));
			util.verifyElementByXpath(logger, nav.tabName(driver, "Main Details"));
			util.clickOn(logger, nav.tabName(driver, "Main Details"));

			// Client Name
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Client Name", "Main Details"));
			util.verifyElementByXpath(logger, nav.label(driver, "Client Name", "Main Details"));
			String valueOfClientName = portal.text(driver, "Client Name").getAttribute("value");

			// Unlisted Client Name
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Unlisted Client Name", "Main Details"));
			util.verifyElementByXpath(logger, nav.label(driver, "Unlisted Client Name", "Main Details"));
			String valueOfUnlistClientName = portal.text(driver, "Unlisted Client Name").getAttribute("value");

			System.out.println(valueOfClientName + " " + valueOfUnlistClientName);
			logger.log(LogStatus.INFO, "Value of Client Name : " + valueOfClientName);
			logger.log(LogStatus.INFO, "Value of Unlisted Client Name : " + valueOfUnlistClientName);

			if ((valueOfClientName.contentEquals("")) && (valueOfUnlistClientName.contentEquals(""))) {
				logger.log(LogStatus.FAIL, "Both Client Name and Unlisted Client Name fields are empty");
				System.out.println("Both Client Name and Unlisted Client Name fields are empty");
			} else if ((valueOfClientName.contentEquals("")) && (valueOfUnlistClientName.contentEquals(""))) {
				logger.log(LogStatus.PASS,
						"Any one of Client Name and Unlisted Client Name fields is filled with values");
				System.out.println("Any one of Client Name and Unlisted Client Name fields is filled with values");
			} else {
				logger.log(LogStatus.FAIL, "Both Client Name and Unlisted Client Name fields are filled with values");
				System.out.println("Both Client Name and Unlisted Client Name fields are filled with values");
			}

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to Handling Client Name Updates");
			util.screenShotAndErrorMsg(logger, e, driver, "Handling Client Name Updates");
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author ankita.a.adhikari
	 * @implNote : for 'GCP Document ID', in 'Main Details' tab, will be
	 *           auto-populated with the value received in the field 'Document ID'
	 *           in payload from GCP Hub
	 */
	@Test
	public void verifyGCPDocumentIDFieldInListandMainDetailsTab() {
		ExtentTest logger = extent.startTest("Verify 'GCP Document ID' value received from GCP Hub",
				"Verify 'GCP Document ID' value received from GCP Hub");
		try {
			List<WebElement> tableTr = driver.findElements(By.xpath("//table[not(contains(@id,'clone'))]//th"));
			int size = tableTr.size();
			int index = 0;
			for (int i = 0; i < size; i++) {
				String str = tableTr.get(i).getText();
				System.out.println(str);
				if (tableTr.get(i).getText().equalsIgnoreCase("GCP Document ID")) {
					index = i + 1;
					break;
				}
			}
			WebElement wb = driver.findElement(By.xpath(
					"//table[not(contains(@id,'clone'))]//tbody[@class='list2_body -sticky-group-headers']//tr[1]//td[" + index + "]"));
			util.clickOn(logger, wb);
			util.pause(logger, "5");
			util.doubleClick(logger, driver, wb);
			util.pause(logger, "10");
			if (driver.findElements(By.xpath("//div[text()='Security prevents writing to this field']")).size() != 0) {
				System.out.println("Element is Non Editable");
				logger.log(LogStatus.PASS, "Element is Non Editable");
				util.clickOn(logger,
						driver.findElement(By.xpath("//a[@title='Cancel (ESC)'][not(@aria-hidden='true')]")));
			} else {
				System.out.println("Element is editable");
				logger.log(LogStatus.FAIL, "Element is Editable");
				util.clickOn(logger,
						driver.findElement(By.xpath("//a[@title='Cancel (ESC)'][not(@aria-hidden='true')]")));
			}

			addColumn(logger, "Source");
			util.scrollByVisibleElement(driver, logger, nav.link(driver, "Source", ""));
			String Source = nav.getTableCellText(logger, driver, "Source", "");
			System.out.println("Source: " + Source);
			addColumn(logger, "Started From");
			util.scrollByVisibleElement(driver, logger, nav.link(driver, "Started From", ""));
			String StartedFrom = nav.getTableCellText(logger, driver, "Started From", "");
			System.out.println("Started From: " + StartedFrom);

			if (Source.equalsIgnoreCase("TRIPP") && StartedFrom.equals("GCP Hub")) {

				logger.log(LogStatus.PASS, "Source Value In Travel Plan: " + Source,
						"Started From Value In Travel Plan is: " + StartedFrom);

				openCreatedGCP_TravelPlanInFormView();

				util.clickOn(logger, nav.tabName(driver, "Main Details"));
				util.scrollByVisibleElement(driver, logger, nav.text(driver, "GCP Document ID", ""));
				util.verifyElementDisabled(logger, nav.text(driver, "GCP Document ID", ""));
				if (util.getElementValue(logger, nav.text(driver, "GCP Document ID", "")).equals(DocumentID)) {
					logger.log(LogStatus.PASS, DocumentID
							+ " is updated successfully and auto-populated with the value received in the field 'Document ID' in payload from GCP Hub");
				} else {
					logger.log(LogStatus.FAIL,
							"GCP Document ID: " + DocumentID + " has Invalid value or updated incorrectly.");
				}
			} else {
				logger.log(LogStatus.INFO,
						"Source Value In Travel Plan not as TRIPP and Started From Value In Travel Plan is not as GCP Hub");
			}

		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL,
					"Unable to verify 'GCP Document ID' value received from GCP Hub : " + DocumentID);
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author ankita.a.adhikari
	 * @implNote : Deletion of Old GCP Document ID field on Travel Plan and Instead
	 *           GCP Document ID & Parent Travel Plan fields on Travel Plan table
	 *           will be used.
	 */
	@Test
	public void verifyDocumentIDShiftedToTP2AndParentTravelPlanCreatedInTP2() {
		ExtentTest logger = extent.startTest(
				"Verify deletion of Old GCP Document ID field and addition of GCP Document ID & Parent Travel Plan fields",
				"Verify deletion of Old GCP Document ID field and addition of GCP Document ID & Parent Travel Plan fields");
		try {
			TP1 = TravelPlanNumber;

			getTravelPlanNumberFromCreatedGCPTravelPlan();
			openCreatedGCP_TravelPlanInFormView();

			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");

			if (driver.findElements(By.xpath(
					"//*[text()='HR Tasks']/following::table/tbody//tr/td[text()='PMG GCP Restaffing, Modified Restaffing or Intra Client Movement']"))
					.size() > 0) {
				logger.log(LogStatus.PASS, "Restaffing HR task is displayed");
			}
			util.clickOn(logger, driver.findElement(By.xpath(
					"//*[text()='HR Tasks']/following::table/tbody//tr/td[text()='PMG GCP Restaffing, Modified Restaffing or Intra Client Movement']/parent::tr/td/a[contains(text(),'HRT')]")));
			util.pause(logger, "5");
			util.clickOn(logger, nav.button(driver, "Create New TP and Close Complete", ""));
			util.pause(logger, "5");

			openTravelPlanTable();

			util.clickOn(logger, portal.label(driver, "All"));
			util.pause(logger, "5");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Search", ""), "GCP Document ID");
			util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", ""), DocumentID);
			util.pause(logger, "3");

			String ProcessType = nav.getTableCellText(logger, driver, "Process Type", "");
			System.out.println("Process Type: " + ProcessType);
			String DocumentID1 = nav.getTableCellText(logger, driver, "GCP Document ID", "");
			System.out.println("GCP Document ID: " + DocumentID1);
			if (TP1 != TravelPlanNumber && ProcessType.equals("Restaffing") && DocumentID1.equals(DocumentID)) {
				logger.log(LogStatus.PASS, TravelPlanNumber + "- : New Travel Plan is created with same Document ID");
				addColumn(logger, "Parent Travel Plan");
				String ParentTravelPlanField = nav.getTableCellText(logger, driver, "Parent Travel Plan", "");
				System.out.println("Parent Travel Plan Value: " + ParentTravelPlanField);
				if (ParentTravelPlanField.contains(TP1)) {
					logger.log(LogStatus.PASS, "Parent Travel Plan Value: " + ParentTravelPlanField);
				} else
					logger.log(LogStatus.FAIL, "Parent Travel Plan has no value or incorrect value");
			} else {
				logger.log(LogStatus.FAIL, "TP2 is not created with same Document ID");
			}

			// verifyColumns(logger , "Old GCP Document ID");
			String OldGCPDocumentID = "Old GCP Document ID";
			util.clickOn(logger, nav.lnk_personalizedIcon);
			util.pause(logger, "5");
			String columns[] = OldGCPDocumentID.split(",");
			Select leftDropdown = new Select(nav.dropdown(driver, "Available", ""));
			Select rightDropdown = new Select(nav.dropdown(driver, "Selected", ""));
			List<WebElement> leftList = leftDropdown.getOptions();
			List<WebElement> rightList = rightDropdown.getOptions();
			for (int i = 0; i < columns.length; i++) {
				for (int j = 0; j < leftList.size(); j++) {
					if (columns[i].equals(leftList.get(j).getText().trim())) {
						logger.log(LogStatus.PASS, "Old GCP Document ID Column is  present " + columns[i]);
						break;
					} else if (j == (leftList.size() - 1)) {
						for (int k = 0; k < rightList.size(); k++) {
							if (columns[i].equals(rightList.get(k).getText().trim())) {
								logger.log(LogStatus.FAIL, "Old GCP Document ID Column is  present " + columns[i]);
								break;
							} else if (k == (rightList.size() - 1)) {
								logger.log(LogStatus.PASS, "Old GCP Document ID Column is not present " + columns[i]);
							}
						}
					}
				}
			}
			util.clickOn(logger, nav.button1(driver, "OK", ""));
			logger.log(LogStatus.PASS, "Old GCP Document ID Column Verification is successful");

		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL,
					"Fail to verify deletion of Old GCP Document ID field and addition of GCP Document ID & Parent Travel Plan fields ");
		}
	}

	/*
	 * //Sumanth
	 */
	@Test
	public void Editabilityoffieldsforrestaffing() {
		ExtentTest logger = extent.startTest("To check editability of fields for Restaffing, Restaffing Modified, ICM",
				"To check editability of fields for Restaffing, Restaffing Modified, ICM");
		try {
			if ((arr1[0].equals("Restaffing")) || arr1[0].equals("Restaffing cancelled")
					|| arr1[0].equals("Restaffing Modified") || arr1[0].equals("Intra Client Movement")
					|| arr1[0].equals("Intra Client Movement cancelled")) {
				logger.log(LogStatus.INFO, "Process Type is " + arr1[0]);
				util.verifyElementByXpath(logger, nav.tabName(driver, "Main Details"));
				util.clickOn(logger, nav.tabName(driver, "Main Details"));

				util.scrollByVisibleElement(driver, logger, nav.label(driver, "GCP Document ID", ""));
				// Gets the value of GCP Document ID field
				String GCPDocumentIDinTP = nav.text(driver, "GCP Document ID", "").getAttribute("value");
				System.out.println(GCPDocumentIDinTP);

				if (GCPDocumentIDinTP.isEmpty()) {

					CheckIfFieldIsBlankAndDisabled(logger, nav.text(driver, "GCP Document ID", ""), "GCP Document ID");
					System.out.println("GCP Document ID is 'Blank'");
					logger.log(LogStatus.PASS, "GCP Document ID is 'Blank'");

					String[] arr = { "Travel Start Date", "Travel End Date", "Street Address if not in office",
							"Client Name", "Project Name", "Charge Code", "Project Accenture Leader",
							"Travel Approver" };
					for (String str : arr) {
						util.scrollByVisibleElement(driver, logger, nav.label(driver, str, "Main Details"));
						util.isEnabled(logger, nav.text(driver, str, "Main Details"));
						util.pause(logger, "1");
					}

				} else {
					CheckIfFieldIsAutoPopulatedAndDisabled(logger, nav.text(driver, "GCP Document ID", ""),
							"GCP Document ID");
					System.out.println("GCP Document ID is " + "" + GCPDocumentIDinTP);
					logger.log(LogStatus.PASS, "GCP Document ID is " + "" + GCPDocumentIDinTP);

					String[] arr = { "Travel Start Date", "Travel End Date", "Street Address if not in office",
							"Project Name", "Charge Code", "Project Accenture Leader", "Travel Approver" };
					for (String str : arr) {
						util.scrollByVisibleElement(driver, logger, nav.label(driver, str, "Main Details"));
						util.verifyElementDisabled(logger, nav.text(driver, str, "Main Details"));
						util.pause(logger, "1");
					}

					util.verifyElementDisabled(logger, nav.text2(driver, "Client Name", "Main Details"));
					// To verify Client Name field is enabled or not if GCP Doc value is not blank
					util.scrollByVisibleElement(driver, logger, nav.text(driver, "Client Name", ""));
					util.verifyElementDisabled(logger, portal.text(driver, "Client Name"));
					util.pause(logger, "1");
				}

				// Irrespective of GCP Document ID value the below fields are non-editable
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Traveler User ID", ""));
				util.verifyElementDisabled(logger, nav.text(driver, "Traveler User ID", ""));
				util.pause(logger, "1");

				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Destination Country/Location", ""));
				util.verifyElementDisabled(logger, nav.text(driver, "Destination Country/Location", ""));
				util.pause(logger, "1");

				// Irrespective of GCP Document ID value the below fields are Editable
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Project Visa Type", "Main Details"));
				util.isEnabled(logger, nav.text(driver, "Project Visa Type", "Main Details"));
				util.pause(logger, "1");

				util.scrollByVisibleElement(driver, logger,
						nav.label(driver, "Destination Office City", "Main Details"));
				util.isEnabled(logger, nav.text(driver, "Destination Office City", "Main Details"));
				util.pause(logger, "1");
			} else {
				logger.log(LogStatus.FAIL, "Editability validation is not possible as Process Type is" + arr1[0]);
			}

		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test method: Failed ==> To check editability of fields for GCP Restaffing, Restaffing Modified, Intra Client Movement");
			logger.log(LogStatus.FAIL,
					"Test method: Failed ==> To check editability of fields for GCP Restaffing, Restaffing Modified, Intra Client Movement");
		}
		extent.endTest(logger);
		extent.flush();
	}

// 	@Test
// 	public void EditabilityoffieldsforrestaffinginListView(ExtentTest logger) {

// 		try {
// 			List<WebElement> tableTr = driver.findElements(By.xpath("//table[not(contains(@id,'clone'))]//th"));
// 			int size = tableTr.size();
// 			int index = 0;
// 			for (int i = 0; i < size; i++) {
// 				String str = tableTr.get(i).getText();
// 				System.out.println(str);
// 				if (tableTr.get(i).getText().equalsIgnoreCase("Process Type")) {
// 					index = i + 1;
// 					break;
// 				}
// 			}
// 			WebElement wb = driver.findElement(By.xpath(
//                     "//table[not(contains(@id,'clone'))]//tbody[@class='list2_body -sticky-group-headers']//tr[1]//td[" + index + "]"));
// //			WebElement wb = driver.findElement(By.xpath(
// //					"//table[not(contains(@id,'clone'))]//tbody[@class='list2_body']//tr[1]//td[" + index + "]"));
// 			util.clickOn(logger, wb);
// 			util.pause(logger, "5");
// 			util.doubleClick(logger, driver, wb);
// 			util.pause(logger, "10");
// 			if (driver.findElements(By.xpath("//div[text()='Security prevents writing to this field']")).size() != 0) {
// 				System.out.println("Element is Non Editable");
// 				logger.log(LogStatus.PASS, "Element is Non Editable");
// 				util.clickOn(logger,
// 						driver.findElement(By.xpath("//a[@title='Cancel (ESC)'][not(@aria-hidden='true')]")));
// 			} else {
// 				System.out.println("Element is editable");
// 				logger.log(LogStatus.FAIL, "Element is Editable");
// 				util.clickOn(logger,
// 						driver.findElement(By.xpath("//a[@title='Cancel (ESC)'][not(@aria-hidden='true')]")));
// 			}
// 			util.pause(logger, "5");

// 			// To check editability of "Destination State/Province/Canton" field in list
// 			// view

// 			util.scrollByVisibleElement(driver, logger, nav.link(driver, "Destination State/Province/Canton", ""));
// 			List<WebElement> tableTr1 = driver.findElements(By.xpath("//table[not(contains(@id,'clone'))]//th"));
// 			int size1 = tableTr1.size();
// 			int index1 = 0;
// 			for (int j = 0; j < size1; j++) {
// 				String str = tableTr1.get(j).getText();
// 				System.out.println(str);
// 				if (tableTr1.get(j).getText().equalsIgnoreCase("Destination State/Province/Canton")) {
// 					index1 = j + 1;
// 					break;
// 				}
// 			}
// //			WebElement wb1 = driver.findElement(By.xpath(
// //					"//table[not(contains(@id,'clone'))]//tbody[@class='list2_body']//tr[1]//td[" + index1 + "]"));
// 			WebElement wb1 = driver.findElement(By.xpath(
//                     "//table[not(contains(@id,'clone'))]//tbody[@class='list2_body -sticky-group-headers']//tr[1]//td[" + index1 + "]"));
// 			util.clickOn(logger, wb1);
// 			util.pause(logger, "5");
// 			util.doubleClick(logger, driver, wb1);
// 			util.pause(logger, "10");
// 			if (driver.findElements(By.xpath("//div[text()='Security prevents writing to this field']")).size() != 0) {
// 				System.out.println("Element is Non Editable");
// 				logger.log(LogStatus.PASS, "Element is Non Editable");
// 				util.clickOn(logger,
// 						driver.findElement(By.xpath("//a[@title='Cancel (ESC)'][not(@aria-hidden='true')]")));
// 			} else {
// 				System.out.println("Element is editable");
// 				logger.log(LogStatus.FAIL, "Element is Editable");
// 				util.clickOn(logger,
// 						driver.findElement(By.xpath("//a[@title='Cancel (ESC)'][not(@aria-hidden='true')]")));
// 			}

// 		} catch (Exception e) {
// 			util.screenShotAndErrorMsg(logger, e, driver,
// 					"Test method: Failed ==> To check editability of fields for GCP Restaffing, Restaffing Modified, Intra Client Movement");
// 			logger.log(LogStatus.FAIL,
// 					"Test method: Failed ==> To check editability of fields for GCP Restaffing, Restaffing Modified, Intra Client Movement");
// 		}
// 		extent.endTest(logger);
// 		extent.flush();

// 	}

	// Garima
	@Parameters({ "HR_Task_Name" })
	@Test
	public void verifyApproverSendBackAndReconfirmButtonNotVisible(String HR_Task_Name) {
		ExtentTest logger = extent.startTest("Verify Buttons not visible in HR task - " + HR_Task_Name,
				"Verify Buttons not visible in HR task - " + HR_Task_Name);
		try {
			if ((getInputData(TestName, "EmployeeHostCountry") != "USA")
					|| (getInputData(TestName, "ProposedVisaType") != "H1B")) {
				logger.log(LogStatus.PASS, "Country and Visa type condition met, Approver task not generated");
				loginAsAdmin();
				util.pause(logger, "5");
				OpenTravelPlan();
				util.pause(logger, "5");
				util.endofpage(logger);
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
				nav.tabName(driver, "Tasks").click();
				util.pause(logger, "2");
				util.verifyElementByXpath(logger, nav.label(driver, "HR Tasks", ""));
				util.pause(logger, "5");

				switch (HR_Task_Name) {
					case "PeopleMobilityConfirmation":
						System.out.println("PMG");
						logger.log(LogStatus.INFO,
								"Closing People Mobility Confirmation HR Task and Validating Buttons");
						util.selectBoxByValue(logger, nav.dropdown(driver, "Search", "HR Tasks"), "Short description");
						util.pause(logger, "10");
						util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", "HR Tasks"),
								"People Mobility Confirmation");
						util.pause(logger, "10");
						util.clickOn(logger, nav.tooltip(driver, "Preview", "", "HR Tasks"));
						util.pause(logger, "3");
						util.waitTillElementIsClickable(logger, driver, nav.link(driver, "Open Record", ""));
						util.clickOn(logger, nav.button(driver, "Open Record", ""));
						CheckIfFieldIsAutoPopulatedAndDisabled(logger, portal.text(driver, "Template"), "Template");
						screenShotAndInfoMsg(logger, driver, "People Mobility Confirmation");

						if (nav.button(driver, "Approver Send Back", "") != null) {
							System.out.println("Approver Send Back is visible ");
							logger.log(LogStatus.FAIL, "Approver Send Back is visible ");
						} else {
							System.out.println("Approver Send Back is not visible ");
							logger.log(LogStatus.PASS, " Approver Reconfirm is not visible ");
						}
						if (nav.button(driver, "Approver Reconfirm", "") != null) {
							System.out.println("Approver Reconfirm is visible ");
							logger.log(LogStatus.FAIL, "Approver Reconfirm is visible ");
						} else {
							System.out.println("Approver Reconfirm is not visible ");
							logger.log(LogStatus.PASS, "Approver Reconfirm is not visible ");
						}
						util.setTextWithEnter(logger, nav.text(driver, "Assigned to", ""), "T39883.01.fulfiller");
						util.pause(logger, "10");
						// util.clickOn(logger, nav.button(driver, "Confirm Travel Request", ""));
						util.clickByJavascriptExecutor(logger, driver,
								findButtonElement(logger, "Confirm Travel Request"));
						util.pause(logger, "5");
						verifyStatusAndStageOfTravelPlan("Pending", "Travel Request Review Complete");
						verifyTACValueOnGCPTP();
						verifyApproverSendBackAndReconfirmButtonNotVisible("StartImmigrationProcess");
						break;

					case "StartImmigrationProcess":
						System.out.println("Immigration");
						logger.log(LogStatus.INFO, "Closing Start Immigration Process HR Task and Validating Buttons");
						util.selectBoxByValue(logger, nav.dropdown(driver, "Search", "HR Tasks"), "Short description");
						util.pause(logger, "10");
						util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", "HR Tasks"),
								"Start Immigration Process");
						util.pause(logger, "10");
						util.clickOn(logger, nav.tooltip(driver, "Preview", "", "HR Tasks"));
						util.pause(logger, "3");
						util.waitTillElementIsClickable(logger, driver, nav.link(driver, "Open Record", ""));
						util.clickOn(logger, nav.button(driver, "Open Record", ""));
						CheckIfFieldIsAutoPopulatedAndDisabled(logger, portal.text(driver, "Template"), "Template");
						screenShotAndInfoMsg(logger, driver, "Start Immigration Process");

						if (nav.button(driver, "Approver Send Back", "") != null) {
							System.out.println("Approver Send Back is visible ");
							logger.log(LogStatus.FAIL, "Approver Send Back is visible ");
						} else {
							System.out.println("Approver Send Back is not visible ");
							logger.log(LogStatus.PASS, " Approver Reconfirm is not visible ");
						}
						if (nav.button(driver, "Approver Reconfirm", "") != null) {
							System.out.println("Approver Reconfirm is visible ");
							logger.log(LogStatus.FAIL, "Approver Reconfirm is visible ");
						} else {
							System.out.println("Approver Reconfirm is not visible ");
							logger.log(LogStatus.PASS, "Approver Reconfirm is not visible ");
						}
						util.setTextWithEnter(logger, nav.text(driver, "Immigration Processing Type", ""),
								"H1B (Home ROTW)");
						util.setTextWithEnter(logger, nav.text(driver, "Assigned to", ""), "T39883.01.fulfiller");

						// util.clickOn(logger, nav.button(driver, "Close Complete", ""));
						util.clickByJavascriptExecutor(logger, driver, findButtonElement(logger, "Close Complete"));

						util.pause(logger, "5");
						verifyStatusAndStageOfTravelPlan("Pending", "Collect and Review Extension Information");

						verifyApproverSendBackAndReconfirmButtonNotVisible("PeopleMobilityExtensionReview");

						break;

					case "PeopleMobilityExtensionReview":
						System.out.println("Extension");
						logger.log(LogStatus.INFO,
								"Closing People Mobility Extension Review HR Task and Validating Buttons");
						util.selectBoxByValue(logger, nav.dropdown(driver, "Search", "HR Tasks"), "Short description");
						util.pause(logger, "10");
						util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", "HR Tasks"),
								"People Mobility Extension Review");
						util.pause(logger, "10");
						util.clickOn(logger, nav.tooltip(driver, "Preview", "", "HR Tasks"));
						util.pause(logger, "3");
						util.waitTillElementIsClickable(logger, driver, nav.link(driver, "Open Record", ""));
						util.clickOn(logger, nav.button(driver, "Open Record", ""));
						CheckIfFieldIsAutoPopulatedAndDisabled(logger, portal.text(driver, "Template"), "Template");
						screenShotAndInfoMsg(logger, driver, "People Mobility Extension Review");

						if (nav.button(driver, "Approver Send Back", "") != null) {
							System.out.println("Approver Send Back is visible ");
							logger.log(LogStatus.FAIL, "Approver Send Back is visible ");
						} else {
							System.out.println("Approver Send Back is not visible ");
							logger.log(LogStatus.PASS, " Approver Reconfirm is not visible ");
						}
						if (nav.button(driver, "Approver Reconfirm", "") != null) {
							System.out.println("Approver Reconfirm is visible ");
							logger.log(LogStatus.FAIL, "Approver Reconfirm is visible ");
						} else {
							System.out.println("Approver Reconfirm is not visible ");
							logger.log(LogStatus.PASS, "Approver Reconfirm is not visible ");
						}
						util.setTextWithEnter(logger, nav.text(driver, "Assigned to", ""), "T39883.01.fulfiller");
						// util.clickOn(logger, nav.button(driver, "Proceed", ""));
						util.clickByJavascriptExecutor(logger, driver, findButtonElement(logger, "Proceed"));

						util.pause(logger, "5");
						util.verifyElementByXpath(logger, nav.tabName(driver, "Activities"));
						util.clickOn(logger, nav.tabName(driver, "Activities"));
						// Activity Log
						if (driver.findElements(By.xpath("//ul[contains(@class,'activities-form')]/li")).size() > 1) {
							logger.log(LogStatus.PASS, "Activity tab is updated");
							List<WebElement> list = driver
									.findElements(By.xpath("//*[@class='h-card h-card_md h-card_comments']"));

							ArrayList<String> ArrayList1 = new ArrayList<String>();
							ArrayList<String> ArrayList2 = new ArrayList<String>();
							String[] str = { "Approval", "Travel Approval Needed" };
							for (String s : str) {
								ArrayList2.add(s);
							}
							Collections.sort(ArrayList2);
							for (int i = 0; i < list.size(); i++) {
								ArrayList1.add(list.get(i).getText());
							}
							if (ArrayList1.equals(ArrayList2) == true) {
								logger.log(LogStatus.FAIL, "Changes are not reflected in Activities tab verififed");
							} else {
								logger.log(LogStatus.PASS, "Changes are reflected correctly in Activity tab verififed");
							}
						} else {
							logger.log(LogStatus.FAIL, "Activity tab is not updated");
						}
						util.scrollByVisibleElement(driver, logger, portal.text(driver, "Not Yet Requested"));
						util.pause(logger, "5");
						screenShotAndInfoMsg(logger, driver, "Activities");
						verifyStatusAndStageOfTravelPlan("Pending", "Petition Processing");
						break;
				}
			} else {
				logger.log(LogStatus.FAIL, "Country and Visa type condition not met");
				System.out.println("Country and Visa type condition not met");
			}

		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Failed");
			logger.log(LogStatus.FAIL, "Not verified");
		}
		extent.endTest(logger);
	}

	@Test
	public void verifyTACValueOnGCPTP() {
		ExtentTest logger = extent.startTest("verify TAC field Value On GCP TP",
				"verify TAC Value On GCP TP");
		try {
			util.clickOn(logger, portal.label(driver, "Main Details"));
			scrollToElementToCenter(portal.label(driver, "Travel Assignment Category"), driver);
			Select s = new Select(portal.dropdown(driver, "Travel Assignment Category"));
			String str = s.getFirstSelectedOption().getText();
			if (str.equalsIgnoreCase("No MSL Required - Service Provided")) {
				logger.log(LogStatus.PASS, "TAC value is auto populated as expected: " + str);
			} else {
				logger.log(LogStatus.FAIL, "TAC value is not auto populated as expected: " + str);
			}
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "unable to verify TAC Value On GCP TP");
			util.screenShotAndErrorMsg(logger, e, driver, "unable to verify TAC Value On GCP TP");
		}
		extent.endTest(logger);
		extent.flush();

	}

	// Rayees
	@Parameters({ "testcaseName" })
	@Test
	public void VerifyFieldsInTopSectionOfGCPTravelPlan(String testcaseName) {
		ExtentTest logger = extent.startTest("Verify Fields in top section of GCP Travel Plan",
				"Verify Fields in top section of GCP Travel Plan");
		try {
			// viewRecord("Number", TravelPlanNumber);
			if (testcaseName.contains("Fulfiller")) {
				String[] fields = getInputData("VerifyFieldsInTopSectionOfGCPTravelPlan", "TopSection").split(",");
				List<String> TopSection = Arrays.asList(fields);
				for (String field_name : TopSection) {
					CheckIfFieldIsAutoPopulatedAndDisabled(logger, portal.text(driver, field_name), field_name);
				}
				CheckIfFieldIsAutoPopulatedAndDisabled(logger, portal.dropdown(driver, "Stage"), "Stage");
			} else {
				CheckIfFieldIsAutoPopulatedAndEditable(logger, portal.text(driver, "Number"), "Number");
				CheckIfFieldIsAutoPopulatedAndDisabled(logger, portal.text(driver, "Home Country/Location"),
						"Home Country/Location");
				CheckIfFieldIsAutoPopulatedAndEditable(logger, portal.text(driver, "Traveler User ID"),
						"Traveler User ID");
				CheckIfFieldIsAutoPopulatedAndDisabled(logger, portal.text(driver, "Destination Country/Location"),
						"Destination Country/Location");
				CheckIfFieldIsAutoPopulatedAndEditable(logger, portal.dropdown(driver, "Stage"), "Stage");
			}
			screenShotAndInfoMsg(logger, driver, "Top Section of GCP Travel Plan");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to login as Fulfiller");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// Rayees
	// verify fields in Traveler profile Tab of GCP Travel plan(Form view)
	@Parameters({ "testcaseName" })
	@Test
	public void VerifyFieldsInGCPTravelerProfileTab(String testcaseName) {
		ExtentTest logger = extent.startTest("Verify Fields in Traveler Profile tab of GCP Travel Plan",
				"Verify Fields in Traveler Profile section of GCP Travel Plan");
		try {
			if (testcaseName.contains("Fulfiller")) {
				convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPTravelerProfileTab",
						"AutoPopulatedAndDisabled", "AutoPopulatedAndDisabled");
				CheckIfFieldIsBlankAndEditable(logger, portal.textArea(driver, "Traveler Profile Comments"),
						"Traveler Profile Comments");
			} else {
				convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPTravelerProfileTab",
						"AutoPopulatedAndDisabledAdmin", "AutoPopulatedAndDisabledAdmin");
				convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPTravelerProfileTab",
						"AutoPopulatedAndEditable", "AutoPopulatedAndEditable");
				CheckIfFieldIsAutoPopulatedAndEditable(logger,
						driver.findElement(
								By.xpath("(//span[contains(text(),'Citizenships')]/following::select)[1]/option")),
						"citizenships");
			}
			convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPTravelerProfileTab",
					"DisplayedAndDisabled", "DisplayedAndDisabled");
			CheckIfFieldIsAutoPopulatedAndEditable(logger, portal.dropdown(driver, "Marital Status"), "Marital Status");
			CheckIfFieldIsBlankAndEditable(logger, portal.textArea(driver, "External Email Address"),
					"External Email Address");
			CheckIfFieldIsBlankAndEditable(logger, portal.textArea(driver, "Contact No./Mobile No."),
					"Contact No./Mobile No.");
			util.scrollByVisibleElement(driver, logger, portal.textArea(driver, "State / Province"));
			screenShotAndInfoMsg(logger, driver, "Traveler Profile Fields 1");
			util.scrollByVisibleElement(driver, logger, portal.textArea(driver, "CareerCounselorNm"));
			screenShotAndInfoMsg(logger, driver, "Traveler Profile Fields 2");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Unable to verify fields in Traveler Profile Tab of GCP Travel plan");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// Rayees
	// verify fields in Main Details Tab of GCP Travel plan(Form view)
	@Parameters({ "testcaseName" })
	@Test
	public void VerifyFieldsInGCPMainDetailsTab(String testcaseName) {
		ExtentTest logger = extent.startTest("Verify Fields in Main Details Tab of GCP Travel Plan",
				"Verify Fields in Main Details Tab of GCP Travel Plan");
		try {
			driver.findElement(By.xpath("//span[text()='Main Details']")).click();
			if (testcaseName.contains("Fulfiller")) {
				CheckIfFieldIsAutoPopulatedAndDisabled(logger, portal.text(driver, "Destination Market Unit"),
						"Destination Market Unit");
				CheckIfFieldIsAutoPopulatedAndDisabled(logger,
						portal.text(driver, "Country/Location Associated to WBS"),
						"Country/Location Associated to WBS");
				convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPMainDetailsTab",
						"BlankAndEditable", "BlankAndEditable");
				convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPMainDetailsTab",
						"BlankAndDisabled", "BlankAndDisabled");
				CheckIfFieldIsAutoPopulatedAndEditable(logger,
						portal.dropdown(driver, "Do you plan for any family members (dependents) to accompany you?"),
						"Do you plan for any family members (dependents) to accompany you?");
			} else {
				CheckIfFieldIsAutoPopulatedAndEditable(logger, portal.text(driver, "Destination Market Unit"),
						"Destination Market Unit");
				CheckIfFieldIsAutoPopulatedAndEditable(logger,
						portal.text(driver, "Country/Location Associated to WBS"),
						"Country/Location Associated to WBS");
				convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPMainDetailsTab",
						"BlankAndEditableAdmin", "BlankAndEditableAdmin");
				convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPMainDetailsTab",
						"BlankAndDisabledAdmin", "BlankAndDisabledAdmin");
				CheckIfFieldIsAutoPopulatedAndEditable(logger,
						portal.dropdown(driver, "Do you plan for any family members (dependents) to accompany you?"),
						"Do you plan for any family members (dependents) to accompany you?");
			}
			String[] ListOfTextArea = { "Policy Detail Comments", "Assignment/Transfer Date Comments",
					"Traveler Role Description",
					"Travel Plan Comments" };
			for (String field_name : ListOfTextArea) {
				CheckIfFieldIsBlankAndEditable(logger, portal.textArea(driver, field_name), field_name);
			}
			convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPMainDetailsTab",
					"AutoPopulatedAndDisabled", "AutoPopulatedAndDisabled");
			convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPMainDetailsTab",
					"BlankAndEditableDropDown", "BlankAndEditableDropDown");
			convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPMainDetailsTab",
					"AutoPopulatedAndEditable", "AutoPopulatedAndEditable");
			convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPMainDetailsTab",
					"AutoPopulatedAndEditableDropDown", "AutoPopulatedAndEditableDropDown");
			CheckIfFieldIsAutoPopulatedAndDisabled(logger, portal.dropdown(driver, "Do you hold another citizenship?"),
					"Do you hold another citizenship?");
			CheckIfFieldIsAutoPopulatedAndDisabled(logger, portal.dropdown(driver, "Work Location"), "Work Location");
			convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInMainDetailsTab", "Checkboxes",
					"BlankAndEditableCheckbox");
			CheckIfFieldIsAutoPopulatedAndDisabled(logger, driver.findElement(By.xpath(
					"(//div[text()='WBS']/following::span[text()='Company Code']/following::input[not(@type='hidden')])[1]")),
					"Company Code");
			// CheckIfFieldIsAutoPopulatedAndDisabled(logger, portal.text(driver, "Company
			// Code"),
			// "Company Code");
			CheckIfFieldIsBlankAndEditable(logger, portal.dropdown(driver, "Business Case Required"),
					"Business Case Required");
			// convertStringArrayToListAndPerformOperation(logger,
			// "VerifyFieldsInGCPMainDetailsTab", "DisplayedAndDisabled",
			// "DisplayedAndDisabled");
			util.scrollByVisibleElement(driver, logger, portal.text(driver, "Legacy ID"));
			screenShotAndInfoMsg(logger, driver, "Main Details Fields 1");
			util.scrollByVisibleElement(driver, logger, portal.textArea(driver, "Policy Detail Comments"));
			screenShotAndInfoMsg(logger, driver, "Main Details Fields 2");
			util.scrollByVisibleElement(driver, logger, portal.text(driver, "People Mobility Billing - Previous"));
			screenShotAndInfoMsg(logger, driver, "Main Details Fields 3");
			util.scrollByVisibleElement(driver, logger, portal.text(driver, "Client Name"));
			screenShotAndInfoMsg(logger, driver, "Main Details Fields 4");
			util.scrollByVisibleElement(driver, logger, portal.text(driver, "Charge Code"));
			screenShotAndInfoMsg(logger, driver, "Main Details Fields 5");
			util.scrollByVisibleElement(driver, logger, portal.text(driver, "Original Home Office"));
			screenShotAndInfoMsg(logger, driver, "Main Details Fields 6");
			util.scrollByVisibleElement(driver, logger, portal.textArea(driver, "Travel Plan Comments"));
			screenShotAndInfoMsg(logger, driver, "Main Details Fields 7");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Unable to verify fields in Main Details Tab of GCP Travel plan");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// Rayees
	// verify fields in Health Insurance Tab of GCP Travel plan(Form view)
	@Test
	public void VerifyFieldsInGCPHealthInsuranceTab() {
		ExtentTest logger = extent.startTest("Verify Fields in Health Insurance Tab of GCP Travel Plan",
				"Verify Fields in Communications Tab of GCP Travel Plan");
		try {
			driver.findElement(By.xpath("//span[text()='Health Insurance']")).click();
			CheckIfFieldIsBlankAndEditable(logger, portal.dropdown(driver, "Global Medical"), "Global Medical");
			CheckIfFieldIsAutoPopulatedAndEditable(logger, portal.text(driver, "Insurance Group Number"),
					"Insurance Group Number");
			convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInHealthInsuranceTab", "BlankAndEditable",
					"BlankAndEditable");
			screenShotAndInfoMsg(logger, driver, "Health Insurance Fields");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Unable to verify fields in Health Insurance Tab of GCP Travel plan");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// Rayees
	// verify fields in Calculations Tab of Travel plan(Form view)
	@Parameters({ "testcaseName" })
	@Test
	public void VerifyFieldsInGCPCalculationsTab(String testcaseName) {
		ExtentTest logger = extent.startTest("Verify Fields in Calculations Tab of GCP Travel Plan",
				"Verify Fields in Communications Tab of GCP Travel Plan");
		try {
			driver.findElement(By.xpath("//span[text()='Calculations']")).click();
			if (testcaseName.contains("Fulfiller")) {
				convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPCalculationsTab",
						"BlankAndDisabled", "BlankAndDisabled");
				// CheckIfFieldIsBlankAndDisabled(logger, portal.text(driver, "Last RP
				// Completed"), "Last RP Completed");
				// CheckIfFieldIsBlankAndDisabled(logger, portal.text(driver, "Last RP Completed
				// Date/Time"),
				// "Last RP Completed Date/Time");
				// CheckIfFieldIsBlankAndDisabled(logger, portal.text(driver, "Last Task
				// Closed"), "Last Task Closed");
			} else {
				convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPCalculationsTab",
						"AutoPopulatedAndDisabledAdmin", "AutoPopulatedAndDisabledAdmin");
				convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPCalculationsTab",
						"AutoPopulatedAndEditableAdmin", "AutoPopulatedAndEditableAdmin");
				convertStringArrayToListAndPerformOperation(logger, "VerifyFieldsInGCPCalculationsTab",
						"BlankAndEditableAdmin", "BlankAndEditableAdmin");
			}
			
			util.scrollByVisibleElement(driver, logger, portal.dropdown(driver, "Activity Type"));
			screenShotAndInfoMsg(logger, driver, "Calculations Tab Fields 1");
			util.scrollByVisibleElement(driver, logger, portal.text(driver, "Immigration Summary"));
			screenShotAndInfoMsg(logger, driver, "Calculations Tab Fields 2");
			util.scrollByVisibleElement(driver, logger, portal.dropdown(driver, "Approval"));
			screenShotAndInfoMsg(logger, driver, "Calculations Tab Fields 3");
			util.scrollByVisibleElement(driver, logger, portal.text(driver, "Csq Attestation Letter"));
			screenShotAndInfoMsg(logger, driver, "Calculations Tab Fields 4");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Unable to verify fields in Calculations Tab of GCP Travel plan");
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author snehal.kalegaonkar
	 *         Validate field in traveler data collection RP
	 */
	@Test
	public void TravelerDataCollectionRP() {
		ExtentTest logger = extent.startTest("Validate Traveler data Colelction RP",
				"Validate Traveler Data Collection RP");
		try {
			util.pause(logger, "3");
			openRP(logger, "Traveler Data Collection");
			util.pause(logger, "2");

			// populate fields
			populateFieldsbyType(logger, "Marital Status", "droplist", getInputData(TestName, "Marital Status"));
			populateFieldsbyType(logger, "Type of employee driven assignment", "droplist",
					getInputData(TestName, "Type of employee driven assignment"));

			// Citizenship used for travel field
			String Citizenshipusedfortravel = getInputData(TestName, "Citizenship used for travel");
			util.verifyElementByXpath(logger, portal.label(driver, "Citizenship used for travel"));
			util.pause(logger, "2");
			util.isEnabled(logger, portal.dropdown(driver, "Citizenship used for travel"));
			util.pause(logger, "1");
			selectFromDroplist2(logger, "Citizenship used for travel", Citizenshipusedfortravel);
			util.pause(logger, "2");
			util.compareTwoStrings(logger, portal.text(driver, "Citizenship used for travel").getAttribute("value"),
					Citizenshipusedfortravel);
			util.pause(logger, "4");

			util.verifyElementByXpath(logger, portal.label(driver, "Do you hold another citizenship?"));
			util.pause(logger, "2");
			util.isEnabled(logger, portal.dropdown(driver, "Do you hold another citizenship?"));
			util.pause(logger, "1");
			selectFromDroplist2(logger, "Do you hold another citizenship?", "No");

			util.pause(logger, "1");
			populateFieldsbyType(logger, "Do you plan for any family members (dependents) to accompany you?",
					"droplist", getInputData(TestName, "Will you be traveling with dependents?"));
			util.verifyElementByXpath(logger, portal.link(driver, "See policy"));
			String SeePolicyURL = portal.link(driver, "See policy").getAttribute("href");
			util.compareTwoStrings(logger, SeePolicyURL, "https://policies.accenture.com/");
			logger.log(LogStatus.PASS, "contact URL is as expected");
			util.verifyElementByXpath(logger, portal.text(driver,
					"to understand the conditions and additional approvals that apply for Accenture\u00a0to cover this cost. "));
			util.clickByJavascriptExecutor(logger, driver, driver.findElement(
					By.xpath("//*[@id='u_gap_approval_confirm']/div/div[1]/label/sp-help-tag/div/div/div[2]/i")));
			populateFieldsbyType(logger,
					"I confirm that I have reviewed Global Watch as well as the list of countries/cities that require Policy 1396 Travel Pre-Approval, and if applicable have submitted the approval request. I am aware that I cannot travel without this approval.",
					"droplist", "Yes");
			util.pause(logger, "2");

			// charge code field
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Charge Code"));
			util.isEnabled(logger, portal.text(driver, "Charge Code"));
			util.pause(logger, "2");
			util.compareTwoStrings(logger, portal.text(driver, "Charge Code").getAttribute("value"), ChargeCode);
			util.pause(logger, "5");
			portal.validationMsg(driver, "Charge code", "You have a valid code");
			util.pause(logger, "5");
			// Is Travel Related to a client field
			util.verifyElementByXpath(logger, portal.label(driver, "Is travel related to a client?"));
			util.pause(logger, "2");
			// util.verifyElementDisabled(logger, portal.text(driver, "Is travel related to
			// a client?"));
			util.isDisabled(logger, portal.text(driver, "Is travel related to a client?"));
			util.pause(logger, "1");
			String IsTravel = driver.findElement(By.xpath(
					"//*[contains(text(),'Is travel related to a client?')]/parent::label/../following-sibling::span//*[contains(text(),'Yes')]"))
					.getText();
			util.compareTwoStrings(logger, IsTravel, "Yes");
			util.pause(logger, "4");
			// Client Name ,Unlisted Client Name,Project Name
			util.verifyElementByXpath(logger, portal.label(driver, "Client Name"));
			util.pause(logger, "2");
			util.isDisabled(logger, portal.text(driver, "Client Name"));
			util.compareTwoStrings(logger, portal.text(driver, "Client Name").getAttribute("value"), ClientName);
			util.pause(logger, "4");

			util.verifyElementByXpath(logger, portal.label(driver, "Unlisted Client Name"));
			util.pause(logger, "2");
			if (portal.text(driver, "Unlisted Client Name").isEnabled() != true) {
				logger.log(LogStatus.INFO, "Unlisted Client Name field is disabled");
			}
			// util.verifyElementReadonlyBasedonAttribute(logger,portal.text(driver,
			// "Unlisted Client Name")," placeholder readyonly");
			util.compareTwoStrings(logger, portal.text(driver, "Unlisted Client Name").getAttribute("value"),
					UnlistedClientName);
			util.pause(logger, "4");

			util.verifyElementByXpath(logger, portal.label(driver, "Project Name"));
			util.pause(logger, "2");
			if (portal.text(driver, "Project Name").isEnabled() != true) {
				logger.log(LogStatus.INFO, "Project Name field is disabled");
			}
			// util.verifyElementReadonlyBasedonAttribute(logger,portal.text(driver,
			// "Project Name"),"placeholder readyonly");
			util.compareTwoStrings(logger, portal.text(driver, "Project Name").getAttribute("value"), ProjectName);
			util.pause(logger, "4");

			// Travel Approver field
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Travel Approver"));
			util.verifyElementByXpath(logger, portal.label(driver, "Travel Approver"));
			util.isEnabled(logger, portal.text(driver, "Travel Approver"));
			util.pause(logger, "2");
			util.compareTwoStrings(logger, portal.text(driver, "Travel Approver").getAttribute("value"),
					TravelApprover);
			util.pause(logger, "5");

			populateFieldsbyType(logger, "Primary Project Contact", "droplist",
					getInputData(TestName, "Primary Project Contact"));

			// Work Location, Destination/Receiving City, Street Address
			util.verifyElementByXpath(logger, portal.label(driver, "Work Location"));
			util.pause(logger, "2");
			util.isDisabled(logger, portal.text(driver, "Work Location"));
			util.pause(logger, "2");
			String WorkLocation = driver.findElement(By.xpath(
					"//*[contains(text(),'Work Location')]/parent::label/../following-sibling::span//*[contains(text(),'Working at Other Location')]"))
					.getText();
			util.compareTwoStrings(logger, WorkLocation, "Working at Other Location");
			util.pause(logger, "3");

			util.verifyElementByXpath(logger, portal.label(driver, "Street Address"));
			if (portal.text(driver, "Street Address").isEnabled() != true) {
				logger.log(LogStatus.INFO, "Street Address field is disabled");
			}
			// util.verifyElementReadonlyBasedonAttribute(logger,portal.text(driver, "Street
			// Address"),"placeholder readyonly");
			util.pause(logger, "2");
			util.compareTwoStrings(logger, portal.text(driver, "Street Address").getAttribute("value"),
					WorkLocationAddress);
			util.pause(logger, "3");

			util.verifyElementByXpath(logger, portal.label(driver, "Destination/Receiving City"));
			util.isDisabled(logger, portal.text(driver, "Destination/Receiving City"));
			util.pause(logger, "2");
			util.compareTwoStrings(logger, portal.text(driver, "Destination/Receiving City").getAttribute("value"),
					DestinationReceivingCity);
			util.pause(logger, "3");

			// populateFieldsbyType(logger, "Destination Office Location",
			// "droplist",getInputData(TestName, "Destination Office Location"));
			populateFieldsbyType(logger, "Zip/Postal Code", "textbox", getInputData(TestName, "Zip/Postal Code"));
			populateFieldsbyType(logger, "Home Housing status while on assignment", "droplist",
					getInputData(TestName, "Home Housing status while on assignment"));
			populateFieldsbyType(logger, "Consulate", "textbox", getInputData(TestName, "Consulate"));
			populateFieldsbyType(logger, "Consulate Address", "textbox", getInputData(TestName, "Consulate Address"));

			util.setText(logger, portal.textArea(driver, "Please provide any additional addresses where you"),
					getInputData(TestName,
							"Please provide any additional addresses where you'll be conducting activities"));
			util.pause(logger, "3");
			populateFieldsbyType(logger, "Do you have a EU citizenship?", "dropdown", "Yes");
			util.pause(logger, "4");

			// non-upload CSQs
			populateRequiredCSQFields(logger);

			// validateCSQs
			if (getInputData(TestName, "validateCSQs").equalsIgnoreCase("Yes")) {
				util.verifyElementByXpath(logger, portal.label(driver, "Are you currently in the Host Country?"));
				util.setText(logger, portal.dropdown(driver, "Are you currently in the Host Country?"), "Yes");
				util.pause(logger, "2");
				util.verifyElementByXpath(logger, portal.label(driver, "Specify the Processing Type"));
				util.setText(logger, portal.dropdown(driver, "Specify the Processing Type"), "H1B Extension");
				util.pause(logger, "2");
				util.verifyElementByXpath(logger, portal.label(driver,
						"Please provide the name of your Accenture leadership in the destination country."));
				util.setText(logger,
						portal.text(driver,
								"Please provide the name of your Accenture leadership in the destination country."),
						"Test");

			}
			// submit
			util.scrollByVisibleElement(driver, logger, portal.button(driver, "Submit"));
			util.clickOn(logger, portal.button(driver, "Submit"));
			util.pause(logger, "5");

		} catch (Exception e) {

			util.screenShotAndErrorMsg(logger, e, driver, "Unable to Validate the traveler data collection RP");
			logger.log(LogStatus.FAIL, "Unable to Validate the traveler data collection RP");
		}

	}

	/**
	 * @author snehal.kalegaonkar
	 *         verify TDC fields value in backend
	 */
	@Test
	public void verifyTDCDfieldsinFulfillerView() {
		ExtentTest logger = extent.startTest("Validate TDC field value in backend",
				"Validate TDC Field value in backend");
		try {
			// login as fulfiller
			UserLoginAsFulfiller();
			util.pause(logger, "2");
			OpenTravelPlan();

			util.pause(logger, "3");
			util.verifyElementByXpath(logger, nav.tabName(driver, "Main Details"));
			util.scrollByVisibleElement(driver, logger, nav.tabName(driver, "Main Details"));
			util.clickOn(logger, nav.tabName(driver, "Main Details"));
			util.pause(logger, "5");

			// Work Location, Destination office City, Street Address if not in office
			util.verifyElementByXpath(logger, nav.label(driver, "Work Location", ""));
			util.pause(logger, "2");
			util.compareTwoStrings(logger, nav.text(driver, "Work Location", "").getAttribute("value"),
					"Working at Other Location");
			util.pause(logger, "3");

			util.verifyElementByXpath(logger, nav.label(driver, "Street Address if not in office", ""));
			util.pause(logger, "2");
			util.compareTwoStrings(logger,
					nav.text(driver, "Street Address if not in office", "").getAttribute("value"), WorkLocationAddress);
			util.pause(logger, "3");

			util.verifyElementByXpath(logger, nav.label(driver, "Destination Office City", ""));
			util.pause(logger, "2");
			util.compareTwoStrings(logger, nav.text(driver, "Destination Office City", "").getAttribute("value"),
					DestinationReceivingCity);
			util.pause(logger, "3");

			// Is travel related to a client field in backend
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Is travel related to a client?", ""));
			util.verifyElementByXpath(logger, nav.label(driver, "Is travel related to a client?", ""));
			util.pause(logger, "2");
			util.compareTwoStrings(logger, nav.text(driver, "Is travel related to a client?", "").getAttribute("value"),
					"Yes");
			util.pause(logger, "2");

			util.verifyElementByXpath(logger, nav.label(driver, "Unlisted Client Name", ""));
			util.pause(logger, "2");
			util.compareTwoStrings(logger, nav.text(driver, "Unlisted Client Name", "").getAttribute("value"),
					UnlistedClientName);
			util.pause(logger, "2");

			util.verifyElementByXpath(logger, nav.label(driver, "Project Name", ""));
			util.pause(logger, "2");
			util.compareTwoStrings(logger, nav.text(driver, "Project Name", "").getAttribute("value"), ProjectName);
			util.pause(logger, "2");

			// Travel Approver field
			util.verifyElementByXpath(logger, nav.label(driver, "Travel Approver", ""));
			util.pause(logger, "2");
			util.compareTwoStrings(logger, nav.text(driver, "Travel Approver", "").getAttribute("value"),
					TravelApprover);
			util.pause(logger, "3");

			// Citizenship used for travel field in backend
			util.verifyElementByXpath(logger, nav.label(driver, "Citizenship used for travel", ""));
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Citizenship used for travel", ""));
			util.pause(logger, "2");
			util.compareTwoStrings(logger, nav.text(driver, "Citizenship used for travel", "").getAttribute("value"),
					Citizenshipusedfortravel);

		} catch (Exception e) {
			// TODO: handle exception
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to Validate TDC field value in backend");
			logger.log(LogStatus.FAIL, "Unable to Validate TDC field value in backend");
		}

	}

	/**
	 * @author ankita.a.adhikari
	 * @implNote : non-H1B visa workflow for GCP Travel Plan with destination
	 *           country other than USA
	 */
	@Parameters({ "HR_Task_Name" })
	@Test
	public void verifyGCPWorkflowForNonUSADestination(String HR_Task_Name) {
		ExtentTest logger = extent.startTest("Verify Buttons not visible in HR task - " + HR_Task_Name,
				"Verify Buttons not visible in HR task - " + HR_Task_Name);
		try {
			if ((getInputData(TestName, "EmployeeHostCountry") != "USA")
					&& (getInputData(TestName, "ProposedVisaType") != "H1B")) {
				logger.log(LogStatus.PASS, "Country and Visa type condition met, Approver task not generated");

				switch (HR_Task_Name) {
					case "PeopleMobilityConfirmation":
						loginAsAdmin();
						OpenTravelPlan();
						verifyStatusAndStageOfTravelPlan("Pending", "People Mobility Review");
						logger.log(LogStatus.PASS, "Country and Visa type condition met, Approver task not generated");
						util.endofpage(logger);
						util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
						nav.tabName(driver, "Tasks").click();
						util.verifyElementByXpath(logger, nav.label(driver, "HR Tasks", ""));
						util.pause(logger, "2");
						util.clickOn(logger, driver.findElement(By.xpath(
								"//*[text()='HR Tasks']/following::table/tbody//tr/td[text()='People Mobility Confirmation']/parent::tr/td/a[contains(text(),'HRT')]")));
						screenShotAndInfoMsg(logger, driver, "People Mobility Confirmation");
						util.setTextWithEnter(logger, nav.text(driver, "Assigned to", ""), "T39883.01.fulfiller");
						util.clickOn(logger, nav.button(driver, "Confirm Travel Request", ""));
						util.pause(logger, "5");
						verifyStatusAndStageOfTravelPlan("Pending", "Travel Request Review Complete");

						verifyGCPWorkflowForNonUSADestination("StartImmigrationProcess");
						break;

					case "StartImmigrationProcess":
						System.out.println("HR TASK - Start Immigration Process");
						util.endofpage(logger);
						util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
						nav.tabName(driver, "Tasks").click();
						util.clickOn(logger, driver.findElement(By.xpath(
								"//*[text()='HR Tasks']/following::table/tbody//tr/td[text()='Start Immigration Process']/parent::tr/td/a[contains(text(),'HRT')]")));
						util.pause(logger, "5");
						screenShotAndInfoMsg(logger, driver, "Start Immigration Process");
						util.setTextWithEnter(logger, nav.text(driver, "Immigration Processing Type", ""),
								getInputData(TestName, "Immigration Processing Type"));
						util.setTextWithEnter(logger, nav.text(driver, "Assigned to", ""), "T39883.01.fulfiller");

						util.clickOn(logger, nav.button(driver, "Close Complete", ""));
						util.pause(logger, "5");
						logger.log(LogStatus.PASS, "HR TASK - Start Immigration Process Completed");
						verifyStatusAndStageOfTravelPlan("Pending", "Business Letters in Progress");

						verifyGCPWorkflowForNonUSADestination("CreateCrossborderAgreement");

						break;

					case "CreateCrossborderAgreement":
						System.out.println("HR TASK - Create Cross-border Agreement");
						util.endofpage(logger);
						util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
						nav.tabName(driver, "Tasks").click();
						util.clickOn(logger, driver.findElement(By.xpath(
								"//*[text()='HR Tasks']/following::table/tbody//tr/td[text()='Create Cross-border Agreement']/parent::tr/td/a[contains(text(),'HRT')]")));
						util.pause(logger, "5");
						util.setTextWithEnter(logger, nav.text(driver, "PMG Document Template", ""),
								getInputData(TestName, "PMG Document Template"));
						util.setTextWithEnter(logger, nav.text(driver, "Assigned to", ""), "T39883.01.fulfiller");
						screenShotAndInfoMsg(logger, driver, "Create Cross-border Agreement");
						util.clickOn(logger, nav.button(driver, "Close Complete", ""));
						util.pause(logger, "5");
						logger.log(LogStatus.PASS, "HR TASK - Create Cross-border Agreement Completed");
						verifyStatusAndStageOfTravelPlan("Pending", "Business Letters in Progress");
						verifyGCPWorkflowForNonUSADestination("CreateEmployeeSupportLetter");

						break;

					case "CreateEmployeeSupportLetter":
						System.out.println("HR TASK - Create Employee Support Letter");
						util.endofpage(logger);
						util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
						nav.tabName(driver, "Tasks").click();
						util.clickOn(logger, driver.findElement(By.xpath(
								"//*[text()='HR Tasks']/following::table/tbody//tr/td[text()='Create Employee Support Letter']/parent::tr/td/a[contains(text(),'HRT')]")));
						util.pause(logger, "5");
						util.setTextWithEnter(logger, nav.text(driver, "Assigned to", ""), "T39883.01.fulfiller");
						util.pause(logger, "5");
						util.clickOn(logger, nav.checkbox(driver, "Template - Not Applicable", ""));
						screenShotAndInfoMsg(logger, driver, "Create Employee Support Letter");
						util.clickOn(logger, nav.button(driver, "Close Complete", ""));
						util.pause(logger, "5");
						logger.log(LogStatus.PASS, "HR TASK - Create Employee Support Letter Completed");

						verifyStatusAndStageOfTravelPlan("Pending", "Business Letters in Progress");
						verifyGCPWorkflowForNonUSADestination("CreateEmployeeInvitationLetter");

						break;

					case "CreateEmployeeInvitationLetter":
						System.out.println("HR TASK - Create Employee Invitation Letter");
						util.endofpage(logger);
						util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
						nav.tabName(driver, "Tasks").click();
						util.clickOn(logger, driver.findElement(By.xpath(
								"//*[text()='HR Tasks']/following::table/tbody//tr/td[text()='Create Employee Invitation Letter']/parent::tr/td/a[contains(text(),'HRT')]")));
						util.pause(logger, "5");
						util.clickOn(logger, nav.checkbox(driver, "Template - Not Applicable", ""));
						util.selectBoxByValue(logger, nav.dropdown(driver, "Electronic Letter to Traveler", ""), "No");
						util.setTextWithEnter(logger, nav.text(driver, "Assigned to", ""), "T39883.01.fulfiller");
						screenShotAndInfoMsg(logger, driver, "Create Employee Invitation Letter");
						util.clickOn(logger, nav.button(driver, "Close Complete", ""));
						util.pause(logger, "5");
						logger.log(LogStatus.PASS, "HR TASK - Create Employee Invitation Letter Completed");
						break;

					case "PrimaryUKRighttoWork":
						System.out.println("HR TASK - Primary UK Right to Work");
						loginAsAdmin();
						OpenTravelPlan();
						verifyStatusAndStageOfTravelPlan("Pending", "Travel Request Complete");
						util.endofpage(logger);
						util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
						nav.tabName(driver, "Tasks").click();
						util.clickOn(logger, driver.findElement(By.xpath(
								"//*[text()='HR Tasks']/following::table/tbody//tr/td[text()='Primary UK Right to Work']/parent::tr/td/a[contains(text(),'HRT')]")));
						util.pause(logger, "5");
						util.setTextWithEnter(logger, nav.text(driver, "Assigned to", ""), "T39883.01.fulfiller");

						screenShotAndInfoMsg(logger, driver, "Primary UK Right to Work");
						util.clickOn(logger, nav.button(driver, "Close Complete", ""));
						util.pause(logger, "5");
						logger.log(LogStatus.PASS, "HR TASK - Primary UK Right to Work Completed");

						verifyStatusAndStageOfTravelPlan("Pending", "Travel Request Complete");

						break;

				}
			} else {
				logger.log(LogStatus.FAIL, "Country and Visa type condition not met");
			}

		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Failed");
			logger.log(LogStatus.FAIL, "Not verified");
		}
		extent.endTest(logger);
	}


	/**
	 * @author ankita.a.adhikari
	 * @implNote : non-H1B visa workflow for GCP Travel Plan with destination
	 *           country other than USA
	 */
	@Test
	public void completeRPsAfterImmigrationProcessingHRTaskClosed() {
		ExtentTest logger = extent
				.startTest("Complete Traveler RPs and Approver RPs After All Immigration HR Task closed by Admin");
		try {
			// Complete Traveler RPs
			CompleteReviewandAccepttheCrossborderTransferAgreementRP(logger);

			// Complete Approver RPs
			loginAsTravelerApprover();
			// Open Travel Plan Number
			util.clickOn(logger, driver.findElement(By.xpath("//*[@id='menu']/ul/li/a[text()='Approval requests ']")));
			util.pause(logger, "10");
			WebElement travelPlanBox = driver.findElement(By.xpath("//*[text()='" + TravelPlanNumber + "']/../../parent::div//following-sibling::div//div//button[text()='Take action']"));
			util.clickOn(logger, travelPlanBox);
			util.waitForPageToLoadCompletely(logger, driver);
			util.pause(logger, "15");

			CompleteUKRighttoWorkConfirmationRP(logger);
			CompleteUKRighttoWorkQuestionsRP(logger);
			CompleteUKRighttoWorkUploadPassportRP(logger);
			CompleteUKRighttoWorkUploadProofofEntryRP(logger);
			CompleteUKRighttoWorkUploadVisaRP(logger);

			// Complete the Last HR Task - Primary UK Right to Work
			verifyGCPWorkflowForNonUSADestination("PrimaryUKRighttoWork");

		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Failed");
			logger.log(LogStatus.FAIL, "Not Completed");
		}
		extent.endTest(logger);
	}

	/**
	 * @author : hermaine.c.t.canania
	 * @implNote : Approval for GCP Travel Plan
	 */
	@Test
	public void travelApproverApprovesTheTravelPlan() {
		ExtentTest logger = extent.startTest("Complete Traveler RPs and Approver RPs After All Immigration HR Task closed by Admin");
		try {

			// Complete Approver RPs
			loginAsTravelerApprover();
			// Open Travel Plan Number
			WebElement hidebutton = driver.findElement(By.xpath("//button[@id='dummyfooter']"));
			util.clickOn(logger, hidebutton);
			Thread.sleep(1000);
			util.clickOn(logger, driver.findElement(By.xpath("//*[@id='menu']/ul/li/a[text()='Approval requests ']")));
			util.pause(logger, "10");
			WebElement travelPlanBox = driver.findElement(By.xpath("//*[text()='" + TravelPlanNumber + "']/../../parent::div//following-sibling::div//div//button[text()='Take action']"));
			util.clickOn(logger, travelPlanBox);
			util.waitForPageToLoadCompletely(logger, driver);
			util.pause(logger, "20");

			openRP(logger, "Collect Travel Approver/Reviewer Information");
			util.pause(logger, "3");

			populateFieldsbyType(logger, "What would you like to do?", "droplist", "Approve");
			populateFieldsbyType(logger, "Please confirm that the WBS provided", "dropdown", "Yes");
			populateFieldsbyType(logger, "Please confirm the WBS provided is associated with the respective client.", "dropdown", "Yes");
			populateFieldsbyType(logger, "Please provide an explanation if the WBS provided is NOT associated", "textbox", "Test automation");
			populateFieldsbyType(logger, "Please provide the name of the Accenture US onsite manager responsible for signing the right to control letter", "textbox", "Test automation");
			populateFieldsbyType(logger, "Provide the enterprise ID of your US project contact.", "textbox", "Test automation");

			util.scrollByVisibleElement(driver, logger, portal.button(driver, "Submit"));
			// submit
			util.clickOn(logger, portal.button(driver, "Submit"));
			util.pause(logger, "5");



		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Failed");
			logger.log(LogStatus.FAIL, "Not Completed");
		}
		extent.endTest(logger);
	}

	@Test
	public void Close_Complete_HR_TASK_GCP_Restaffing_RestaffingModified_IntraClientMovement() {
		ExtentTest logger = extent.startTest(
				"Close Complete HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement",
				"Close Complete HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
		try {
			openGCPTravelPlanAndVerifyProcessType(logger);
			util.pause(logger, "5");
			util.endofpage(logger);
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			System.out.println(EmployeeHostCountry);
			if (EmployeeHostCountry.contains("USA")) {
				Open_HR_TASK_Eligibility_Check_for_GCP();
				complete_HR_Task_Eligibility_Check_For_GCP_TravelPlan();
				util.pause(logger, "1");
				util.endofpage(logger);
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
				nav.tabName(driver, "Tasks").click();
				util.pause(logger, "2");
			}
			Open_HR_TASK_GCP_Restaffing_RestaffingModified_IntraClientMovement();
			VerifyPopulateAssignedTo(logger, getInputData(TestName, "FulfillerID"));
			util.verifyNullTextByValue(logger, nav.text(driver, "Description", ""));
			util.setText(logger, nav.text(driver, "Description", ""), getInputData(TestName, "Description"));
			util.verifyNullTextByValue(logger, nav.text(driver, "Work notes", ""));
			util.setText(logger, driver.findElement(By.xpath(
					"//*[text()='Work notes']/parent::label/parent::div[not(@aria-hidden='true')]//textarea[@id='activity-stream-textarea']")),
					getInputData(TestName, "WorkNotes"));
			Complete_HR_TASK_GCP_Restaffing_RestaffingModified_IntraClientMovement();
			logger.log(LogStatus.PASS,
					"Test method: Passed ==> Close Complete HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test methhod: Failed ==> Close Complete HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
			logger.log(LogStatus.FAIL,
					"Test method: Failed ==> Close Complete HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void openGCPTravelPlanAndVerifyProcessType(ExtentTest logger) {
		TestUser = getInputData(TestName, "TestUser");
		if (TestUser.contains("PMG ADMIN")) {
			loginAsAdmin();
			navigateToNavPageFromPortal();
		} else if (TestUser.contains("PMG FULFILLER")) {
			UserLoginAsFulfiller();
			navigateToNavPageFromPortal();
		} else {
			logger.log(LogStatus.INFO,
					"USER IS ENTERED AS " + TestUser + "./n user has to be either PMG ADMIN OR PMG FULFILLER");
			logger.log(LogStatus.FAIL, "Login failed");
		}
		// getTravelPlanNumberFromCreatedGCPTravelPlan();
		openTravelPlanTable();
		// OpenTravelPlan();
		addColumn(logger, "Number");

		util.selectBoxByValue(logger, driver.findElement(By.xpath("//select[contains(@aria-label,'Search')]")),
				"Number");
		util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", ""), TravelPlanNumber);
		util.pause(logger, "3");
		addColumn(logger, "Process Type");
		util.scrollByVisibleElement(driver, logger, nav.link(driver, "Process Type", ""));
		String ProcessTypeValueInTravelPlan = nav.getTableCellText(logger, driver, "Process Type", "");
		// ProcessType = getInputData(TestName, "Process Type");
		util.compareTwoStrings(logger, ProcessTypeValueInTravelPlan, arr1[0]);// arr1[0] is updated process type
		addColumn(logger, "Started From");
		util.scrollByVisibleElement(driver, logger, nav.link(driver, "Started From", ""));
		String StartedFromValueInTravelPlan = nav.getTableCellText(logger, driver, "Started From", "");
		util.compareTwoStrings(logger, StartedFromValueInTravelPlan, "GCP Hub");
		openCreatedGCP_TravelPlanInFormView();
	}

	@Test
	public void Open_HR_TASK_Eligibility_Check_for_GCP() {
		ExtentTest logger = extent.startTest("Open HR TASK : Eligibility Check For GCP",
				"Open HR TASK : Eligibility Check For GCP");
		try {
			util.pause(logger, "5");
			util.endofpage(logger);
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, "Eligibility Check for GCP", "Short description", "HR Tasks", "Work in Progress");
		} catch (Exception e) {
			// TODO: handle exception
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author k.p.balakrishnan
	 */
	@Test
	public void Complete_HR_TASK_GCP_Restaffing_RestaffingModified_IntraClientMovement() {
		ExtentTest logger = extent.startTest(
				"Close Complete HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement",
				"Close Complete HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
		try {
			ActionButton = getInputData(TestName, "Restaffing_RestaffingModified_IntraClientMovement_Action_Button");
			switch (ActionButton) {
				case "Update":
					validateWorkNotesActivity();
					ValidateWorkNotesActivityForVisaAndCity(Boolean.parseBoolean(getInputData(TestName, "validCity")),
							Boolean.parseBoolean(getInputData(TestName, "validVisaType")), "");
					util.clickOn(logger, nav.button(driver, "Update", ""));
					util.waitForPageToLoadCompletely(logger, driver);
					util.pause(logger, "5");
					break;

				case "Create New TP and Close Complete":
					validateWorkNotesActivity();
					ValidateWorkNotesActivityForVisaAndCity(Boolean.parseBoolean(getInputData(TestName, "validCity")),
							Boolean.parseBoolean(getInputData(TestName, "validVisaType")), "");
					util.clickOn(logger, nav.button(driver, "Create New TP and Close Complete", ""));
					util.waitForPageToLoadCompletely(logger, driver);
					util.pause(logger, "5");
					break;
				case "Overwrite This TP and Close Complete":
					validateWorkNotesActivity();
					ValidateWorkNotesActivityForVisaAndCity(Boolean.parseBoolean(getInputData(TestName, "validCity")),
							Boolean.parseBoolean(getInputData(TestName, "validVisaType")), "");
					util.clickOn(logger, nav.button(driver, "Overwrite This TP and Close Complete", ""));
					util.waitForPageToLoadCompletely(logger, driver);
					util.pause(logger, "5");
					// validate_Updated_Values_In_Travel_Plan__From_GCP_Restaffing_RestaffingModified_IntraClientMovement_HR_TASK();
					// util.waitForPageToLoadCompletely(logger, driver);
					// util.pause(logger, "5");
					break;

				default:
					logger.log(LogStatus.INFO, "Please enter valid action button");
					logger.log(LogStatus.FAIL, "Invalid action button: " + ActionButton);
					break;
			}
			logger.log(LogStatus.PASS,
					"Test method: Passed ==> Close Complete HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test methhod: Close Complete Failed ==> HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
			logger.log(LogStatus.FAIL,
					"Test method: Failed ==> Close Complete HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// Garima
	/**
	 * @author k.p.balakrishnan , sai.v.kotapalli
	 * @param validCityName
	 * @param validVisaType
	 * @param HR_Task
	 */
	@Test
	public void ValidateWorkNotesActivityForVisaAndCity(boolean validCityName, boolean validVisaType, String HR_Task) {
		ExtentTest logger = extent.startTest("Verify Work Notes For Visa And City",
				"Verify Work Notes For Visa And City");
		try {
			WorkNoteActivity2 = WorkNoteActivityLogDataForInvalidDestinationAndProjectVisaType(logger);
			if (validCityName == true && validVisaType == true) {
				if (WorkNoteActivity2.isEmpty() == true) {
					logger.log(LogStatus.PASS, "Work Note activity is not displayed.");
				} else if (WorkNoteActivity2.contains("Current")) {
					logger.log(LogStatus.PASS, "Work Note activity is not displayed.");
				} else {
					logger.log(LogStatus.FAIL, "Invalid Update.");
				}
			} else if (validCityName == true && validVisaType == false) {
				if (HR_Task.contains("Eligibility Check for GCP")
						&& WorkNoteActivity2.contains("Destination Office City")) {
					if ((WorkNoteActivity2.contains("Destination Office City = " + EmployeeHostCity))) {
						logger.log(LogStatus.PASS,
								"Destination Office City = " + EmployeeHostCity + " is displayed in activity notes");
					} else {
						logger.log(LogStatus.FAIL, "Invalid Update.");
					}
				} else if (WorkNoteActivity2.contains("Destination Office City")) {
					if ((WorkNoteActivity2.contains("Destination Office City = " + arr1[5]))) {
						logger.log(LogStatus.PASS,
								"Destination Office City = " + arr1[5] + " is displayed in activity notes");
					} else {
						logger.log(LogStatus.FAIL, "Invalid Update.");
					}
				}
			} else if (validCityName == false && validVisaType == true) {
				if (HR_Task.contains("Eligibility Check for GCP")
						&& WorkNoteActivity2.contains("Project Visa Type = ")) {
					if ((WorkNoteActivity2.contains("Project Visa Type = " + ProposedVisaType))) {
						logger.log(LogStatus.PASS,
								"Project Visa Type = " + ProposedVisaType + " is displayed in activity notes");
					} else {
						logger.log(LogStatus.FAIL, "Invalid Update.");
					}

				} else if (WorkNoteActivity2.contains("Project Visa Type = ")) {
					if ((WorkNoteActivity2.contains("Destination Office City = " + arr1[13]))) {
						logger.log(LogStatus.PASS,
								"Destination Office City = " + arr1[13] + " is displayed in activity notes");
					} else {
						logger.log(LogStatus.FAIL, "Invalid Update.");
					}
				}

			} else if (validCityName == false && validVisaType == false) {
				if (HR_Task.contains("Eligibility Check for GCP") && WorkNoteActivity2.contains("Project Visa Type = ")
						&& WorkNoteActivity2.contains("Destination Office City")) {
					if ((WorkNoteActivity2.contains("Project Visa Type = " + ProposedVisaType))) {
						logger.log(LogStatus.PASS,
								"Project Visa Type = " + ProposedVisaType + " is displayed in activity notes");
					} else {
						logger.log(LogStatus.FAIL, "Invalid Update.");
					}

					if ((WorkNoteActivity2.contains("Destination Office City = " + EmployeeHostCity))) {
						logger.log(LogStatus.PASS,
								"Destination Office City = " + EmployeeHostCity + " is displayed in activity notes");
					} else {
						logger.log(LogStatus.FAIL, "Invalid Update.");
					}

				} else if (WorkNoteActivity2.contains("Project Visa Type = ")
						&& WorkNoteActivity2.contains("Destination Office City")) {
					if ((WorkNoteActivity2.contains("Destination Office City = " + arr1[13]))) {
						logger.log(LogStatus.PASS,
								"Destination Office City = " + arr1[13] + " is displayed in activity notes");
					} else {
						logger.log(LogStatus.FAIL, "Invalid Update.");
					}

					if ((WorkNoteActivity2.contains("Destination Office City = " + arr1[5]))) {
						logger.log(LogStatus.PASS,
								"Destination Office City = " + arr1[5] + " is displayed in activity notes");
					} else {
						logger.log(LogStatus.FAIL, "Invalid Update.");
					}
				}
			}

		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Failed");
			logger.log(LogStatus.FAIL, "Not verified");
		}
		extent.endTest(logger);
	}

	@Test
	public void Open_HR_TASK_GCP_Restaffing_RestaffingModified_IntraClientMovement() {
		ExtentTest logger = extent.startTest(
				"Open HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement",
				"Open HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
		try {
			util.pause(logger, "5");
			util.endofpage(logger);
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, "PMG GCP Restaffing, Modified Restaffing or Intra Client Movement", "Short description",
					"HR Tasks", "Work in Progress");
		} catch (Exception e) {
			// TODO: handle exception
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author k.p.balakrishnan
	 */
	@Test
	public void complete_HR_Task_Eligibility_Check_For_GCP_TravelPlan() {
		ExtentTest logger = extent.startTest("Complete GCP HR TASK: Eligibility Check for GCP",
				"Complete GCP HR TASK: Eligibility Check for GCP.");
		try {
			// Fields:
			// 1. Number
			util.verifyElementByXpath(logger, nav.label(driver, "Number", ""));
			HRTaskNumber_Eligibility_Check_for_GCP = util.getElementValue(logger, nav.text(driver, "Number", ""));
			logger.log(LogStatus.INFO,
					"HRTaskNumber_Eligibility_Check_for_GCP: " + HRTaskNumber_Eligibility_Check_for_GCP);
			if (HRTaskNumber_Eligibility_Check_for_GCP.contains("HRT")) {
				logger.log(LogStatus.PASS, HRTaskNumber_Eligibility_Check_for_GCP + " is created with uunique number");
			} else {
				logger.log(LogStatus.FAIL,
						HRTaskNumber_Eligibility_Check_for_GCP + " is not created with uunique number");
			}
			util.verifyElementDisabled(logger, nav.text(driver, "Number", ""));

			// 2. Template
			util.verifyElementByXpath(logger, nav.label(driver, "Template", ""));
			Template_Eligibility_Check_for_GCP = util.getElementValue(logger, nav.text(driver, "Template", ""));
			if (Template_Eligibility_Check_for_GCP.equalsIgnoreCase("PMG GCP Visa Check")) {
				logger.log(LogStatus.PASS, "PMG GCP Visa Check is present in the template field");
			} else {
				logger.log(LogStatus.FAIL, "PMG GCP Visa Check is not present in the template field");
			}
			util.verifyElementDisabled(logger, nav.text(driver, "Template", ""));

			// 3. HR Case
			util.verifyElementByXpath(logger, nav.label(driver, "HR Case", ""));
			HRCaseNumber_Eligibility_Check_for_GCP = util.getElementValue(logger, nav.text(driver, "HR Case", ""));
			logger.log(LogStatus.INFO,
					"HRCaseNumber_Eligibility_Check_for_GCP: " + HRCaseNumber_Eligibility_Check_for_GCP);
			if (HRCaseNumber_Eligibility_Check_for_GCP.contains("HRC")) {
				logger.log(LogStatus.PASS, HRCaseNumber_Eligibility_Check_for_GCP + " is created with uunique number");
			} else {
				logger.log(LogStatus.FAIL,
						HRCaseNumber_Eligibility_Check_for_GCP + " is not created with uunique number");
			}
			util.verifyElementDisabled(logger, nav.text(driver, "HR Case", ""));

			// 4. State
			util.verifyElementByXpath(logger, nav.label(driver, "State", ""));
			State_Eligibility_Check_for_GCP = util.getElementValue(logger, nav.dropdown(driver, "State", ""));
			logger.log(LogStatus.INFO, "State_Eligibility_Check_for_GCP: " + State_Eligibility_Check_for_GCP);
			if (State_Eligibility_Check_for_GCP.contains("Work in Progress")) {
				logger.log(LogStatus.PASS, "State_Eligibility_Check_for_GCP  is " + State_Eligibility_Check_for_GCP);
			} else {
				logger.log(LogStatus.FAIL,
						"State_Eligibility_Check_for_GCP  is not Work in Progress. It is observed as "
								+ State_Eligibility_Check_for_GCP);
			}
			// util.verifyElementDisabled(logger, nav.text(driver, "State", ""));

			// 5. Travel Plan
			util.verifyElementByXpath(logger, nav.label(driver, "Travel Plan", ""));
			TravelPlanNumber_Eligibility_Check_for_GCP = util.getElementValue(logger,
					nav.text(driver, "Travel Plan", ""));
			logger.log(LogStatus.INFO,
					"TravelPlanNumber_Eligibility_Check_for_GCP: " + TravelPlanNumber_Eligibility_Check_for_GCP);
			if (TravelPlanNumber_Eligibility_Check_for_GCP.contains(TravelPlanNumber)) {
				logger.log(LogStatus.PASS,
						TravelPlanNumber_Eligibility_Check_for_GCP + " is associated with correct HR Task");
			} else {
				logger.log(LogStatus.FAIL,
						TravelPlanNumber_Eligibility_Check_for_GCP + " is not associated with correct HR Task");
			}
			util.verifyElementDisabled(logger, nav.text(driver, "Travel Plan", ""));

			// 6. Assignment group
			util.verifyElementByXpath(logger, nav.label(driver, "Assignment group", ""));
			AssignmentGroup_Eligibility_Check_for_GCP = util.getElementValue(logger,
					nav.text(driver, "Assignment group", ""));
			logger.log(LogStatus.INFO,
					"AssignmentGroup_Eligibility_Check_for_GCP: " + AssignmentGroup_Eligibility_Check_for_GCP);
			if (AssignmentGroup_Eligibility_Check_for_GCP.isEmpty() == false) {
				logger.log(LogStatus.PASS,
						"AssignmentGroup_Eligibility_Check_for_GCP is: " + AssignmentGroup_Eligibility_Check_for_GCP);
			} else {
				logger.log(LogStatus.FAIL, "AssignmentGroup_Eligibility_Check_for_GCP is null("
						+ AssignmentGroup_Eligibility_Check_for_GCP + ")");
			}
			if (nav.text(driver, "Assignment group", "").isEnabled() == true) {
				logger.log(LogStatus.PASS, "Assignment group is enabled and editable");
			} else {
				logger.log(LogStatus.FAIL, "Assignment group is not enabled");
			}

			// 7. Assigned To
			util.verifyElementByXpath(logger, nav.label(driver, "Assigned to", ""));
			AssignedTo_Eligibility_Check_for_GCP = util.getElementValue(logger, nav.text(driver, "Assigned to", ""));
			if (AssignedTo_Eligibility_Check_for_GCP.isEmpty() == true) {
				logger.log(LogStatus.PASS, "Assigned to value is null");
			} else {
				logger.log(LogStatus.FAIL, "Assigned to value is not null");
			}
			if (nav.text(driver, "Assigned to", "").isEnabled() == true) {
				logger.log(LogStatus.PASS, "Assigned to is enabled and editable");
			} else {
				logger.log(LogStatus.FAIL, "Assigned to is not enabled");
			}

			// 8. Is Traveler Eligible
			util.verifyElementByXpath(logger, nav.label(driver, "Is Traveler Eligible", ""));
			// util.verifyDropdownValues(logger, nav.dropdown(driver, "Is Traveler
			// Eligible", ""), "Yes");
			// util.verifyDropdownValues(logger, nav.dropdown(driver, "Is Traveler
			// Eligible", ""), "No");
			// util.verifyDropdownValues(logger, nav.dropdown(driver, "Is Traveler
			// Eligible", ""), "-- None --");
			String[] dropdownValues = { "No", "-- None --", "Yes" };
			// System.out.println(dropdownValue);
			// String[] dropdownValues= dropdownValue.split(",");
			for (int i = 0; i < dropdownValues.length; i++) {
				util.selectBoxByValue(logger, nav.dropdown(driver, "Is Traveler Eligible", ""), dropdownValues[i]);
				util.compareTwoStrings(logger,
						util.getSelectedValueFromDropdown(logger, nav.dropdown(driver, "Is Traveler Eligible", "")),
						dropdownValues[i]);
				;
				screenShotAndInfoMsg(logger, driver,
						dropdownValues[i] + "value is present in dropdown value of Is Traveler Eligible");
				logger.log(LogStatus.PASS,
						dropdownValues[i] + "value is present in dropdown value : Is Traveler Eligible");
			}
			if (nav.mandatoryField(driver, "Is Traveler Eligible", "") != null) {
				logger.log(LogStatus.PASS, "Is Traveler Eligible is a mandatory field");
			} else {
				logger.log(LogStatus.FAIL, "Is Traveler Eligible is not a mandatory field");
			}

			// 9. Project Visa Type
			util.verifyElementByXpath(logger, nav.label(driver, "Project Visa Type", ""));
			if (nav.mandatoryField(driver, "Project Visa Type", "") != null) {
				logger.log(LogStatus.PASS, "Project Visa Type is a mandatory field");
			} else {
				logger.log(LogStatus.FAIL, "Project Visa Type is not a mandatory field");
			}

			URL_For_HRTask_EligibilityCheckForGCP = driver.getCurrentUrl();
			// browserHelper.navigateTo(logger, URL_For_HRTask_EligibilityCheckForGCP);
			// util.waitForPageToLoadCompletely(logger, driver);
			// util.pause(logger, "3");
			// Fill data in HR Task:
			// A. Is Traveler Eligible
			util.selectBoxByValue(logger, nav.dropdown(driver, "Is Traveler Eligible", ""), IsTravelerEligible);
			String getIsTravelerEligibleValue = util.getSelectedValueFromDropdown(logger,
					nav.dropdown(driver, "Is Traveler Eligible", ""));
			util.pause(logger, "1");

			// B. Project Visa Type
			if (ProjectVisaTypeInEligibilityCheckForGCP.equals(null)) {
				logger.log(LogStatus.INFO, "ProjectVisaTypeInEligibilityCheckForGCP - FIELD VALUE IN EXCEL IS NULL");
				logger.log(LogStatus.FAIL, "ProjectVisaTypeInEligibilityCheckForGCP - FIELD VALUE IN EXCEL IS NULL");
			}
			if (getIsTravelerEligibleValue.equals("Yes")) {
				// 9. Project Visa Type
				util.verifyElementByXpath(logger, nav.label(driver, "Project Visa Type", ""));
				if (nav.mandatoryField(driver, "Project Visa Type", "") != null) {
					logger.log(LogStatus.PASS, "Project Visa Type is a mandatory field");
				} else {
					logger.log(LogStatus.FAIL, "Project Visa Type is not a mandatory field");
				}

				if (ProjectVisaType.equals(ProjectVisaTypeInEligibilityCheckForGCP)) {
					// verify auto-population
					if (util.getSelectedValueFromDropdown(logger, nav.dropdown(driver, "Project Visa Type", ""))
							.equals(ProjectVisaTypeInEligibilityCheckForGCP)) {
						logger.log(LogStatus.PASS,
								"project visa typr value: " + ProjectVisaType + " is auto-populated.");
					} else {
						logger.log(LogStatus.PASS,
								"project visa typr value: " + ProjectVisaType + " is not auto-populated.");
					}
				} else {
					util.selectBoxByVisibleText(logger, nav.dropdown(driver, "Project Visa Type", ""),
							ProjectVisaTypeInEligibilityCheckForGCP);
				}
			} else if (getIsTravelerEligibleValue.equals("No")) {
				util.verifyElementNotDisplayed(logger, nav.label(driver, "Project Visa Type", ""));
				logger.log(LogStatus.PASS, "project visa type field is not auto-populated.");
			} else if (getIsTravelerEligibleValue.equals("-- None --")) {
				util.verifyElementNotDisplayed(logger, nav.label(driver, "Project Visa Type", ""));
				logger.log(LogStatus.PASS, "project visa type field is not displayed.");
			}
			util.pause(logger, "1");

			// C, 10. Reuse Existing H1B Nomination Travel Plan
			if (getIsTravelerEligibleValue.equals("Yes") && ProjectVisaTypeInEligibilityCheckForGCP.equals("H1B")
					&& isH1BTravelPlanCreated == true) {
				util.verifyElementByXpath(logger, nav.label(driver, "Reuse Existing H1B Nomination Travel Plan", ""));
				util.selectBoxByVisibleText(logger,
						nav.dropdown(driver, "Reuse Existing H1B Nomination Travel Plan", ""),
						H1BNominatedTravelPlanName);
				screenShotAndInfoMsg(logger, driver, "Reuse Existing H1B Nomination Travel Plan");
				logger.log(LogStatus.PASS,
						"Overwriiten of H1B Nominated travel plan: " + H1BNominatedTravelPlanNumber + " is possible.");
			} else if (getIsTravelerEligibleValue.equals("Yes") && ProjectVisaTypeInEligibilityCheckForGCP.equals("H1B")
					&& isH1BTravelPlanCreated == false) {
				util.verifyElementNotDisplayed(logger, nav.label(driver, "Project Visa Type", ""));
				logger.log(LogStatus.INFO, "Overwriiten of H1B Nominated travel plan is not possible.");
				logger.log(LogStatus.PASS, "project visa type field is not displayed.");
			} else if (getIsTravelerEligibleValue.equals("No")) {
				logger.log(LogStatus.PASS, "project visa type field is not displayed.");
			} else if (getIsTravelerEligibleValue.equals("Yes") && ProjectVisaTypeInEligibilityCheckForGCP != "H1B"
					&& isH1BTravelPlanCreated == true) {
				logger.log(LogStatus.PASS, "project visa type field is not displayed.");
			} else {
				logger.log(LogStatus.FAIL, "project visa type field is not displayed.");
			}

			// D. Assigned to
			util.setText(logger, nav.text(driver, "Assigned to", ""), AssignedTo_Eligibility_Check_for_GCP);
			util.pause(logger, "1");

			// E. Description
			util.verifyElementByXpath(logger, nav.label(driver, "Description", ""));
			util.setText(logger, nav.text(driver, "Description", ""), description);
			util.pause(logger, "1");

			// F. 'WorkNotes
			util.verifyElementByXpath(logger, nav.label(driver, "Work notes", ""));
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Work notes", ""));
			util.clickOn(logger, nav.text(driver, "Work notes", ""));
			util.setText(logger, nav.text(driver, "Work notes", ""), worknotes);
			util.pause(logger, "1");

			// HRTaskAction_EligibilityCheckForGCP;
			util.verifyElementByXpath(logger, nav.button(driver, HRTaskAction_EligibilityCheckForGCP, ""));
			util.scrollByVisibleElement(driver, logger, nav.button(driver, HRTaskAction_EligibilityCheckForGCP, ""));
			util.clickOn(logger, nav.button(driver, HRTaskAction_EligibilityCheckForGCP, ""));
			logger.log(LogStatus.PASS,
					"HR_Task_Eligibility_Check_for_GCP is successfully : " + HRTaskAction_EligibilityCheckForGCP);
		} catch (Exception e) {
			logger.log(LogStatus.FAIL,
					"HR_Task_Eligibility_Check_for_GCP is not successfully : " + HRTaskAction_EligibilityCheckForGCP);
			util.screenShotAndErrorMsg(logger, e, driver,
					"HR_Task_Eligibility_Check_for_GCP is not successfully : " + HRTaskAction_EligibilityCheckForGCP);
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author k.p.balakrishnan
	 */
	@Test
	public void validateWorkNotesActivity() {
		ExtentTest logger = extent.startTest("Validate Work Notes Activity", "Validate Work Notes Activity");
		try {
			WorkNoteActivity = WorkNoteActivityLogData(logger);
			logger.log(LogStatus.INFO, "Work Note Activity : " + WorkNoteActivity);
			if (WorkNoteActivity.isEmpty() == false) {
				AssignmentStartDate = AssignmentStartDate.split("T")[0];
				FinalGCPEndDttm = FinalGCPEndDttm.split("T")[0];
				arr1[7] = arr1[7].split("T")[0];
				arr1[8] = arr1[8].split("T")[0];
				System.out.println(AssignmentStartDate.split("T")[0]);
				System.out.println(FinalGCPEndDttm.split("T")[0]);
				logger.log(LogStatus.INFO, "Travel Start Date :" + AssignmentStartDate.split("T")[0]);
				logger.log(LogStatus.INFO, "Travel End Date :" + FinalGCPEndDttm.split("T")[0]);
				String[] InitialGCPData = { ProcessType, EnterpriseID, EmployeeHostCountry, EmployeeHostState,
						EmployeeHostCity, WorkLocationAddress, ClientName, AssignmentStartDate, FinalGCPEndDttm,
						ProjectName, ProjectAccentureLeader, TravelApprover, ChargeCode, ProposedVisaType };
				String[] FieldNames = { "", "Traveler User ID", "Destination Country/Location",
						"Destination State/Province/Canton", "Destination Office City",
						"Street Address if not in office", "Client Name or Unlisted Client Name", "Travel Start Date",
						"Travel End Date", "Project Name", "Project Accenture Leader", "Travel Approver", "Charge Code",
						"" };

				for (int i = 1; i < arr1.length - 2; i++) {
					if (arr1[i].equals(InitialGCPData[i])) {
						if (WorkNoteActivity.contains("Current " + FieldNames[i] + " - " + InitialGCPData[i] + " | "
								+ "New " + FieldNames[i] + " - " + arr1[i])) {
							logger.log(LogStatus.FAIL, FieldNames[i]
									+ " is present in work note activity though current and new value are same.");
						} else {
							logger.log(LogStatus.INFO,
									"InitialGCPData[i] : " + InitialGCPData[i] + "\nFieldNames[i] : " + FieldNames[i]);
							logger.log(LogStatus.PASS,
									FieldNames[i] + " is not present as the value in work note activity tab.");
						}
					} else { // arr1[i] != InitialGCPData[i]
						if (WorkNoteActivity.contains("Current " + FieldNames[i] + " - " + InitialGCPData[i] + " | "
								+ "New " + FieldNames[i] + " - " + arr1[i])) {
							System.out.println("Current " + FieldNames[i] + " - " + InitialGCPData[i] + " | " + "New "
									+ FieldNames[i] + " - " + arr1[i]);
							logger.log(LogStatus.INFO, "Current " + FieldNames[i] + " - " + InitialGCPData[i] + " | "
									+ "New " + FieldNames[i] + " - " + arr1[i]);
							logger.log(LogStatus.INFO,
									"InitialGCPData[i] : " + InitialGCPData[i] + "\nFieldNames[i] : " + FieldNames[i]);
							logger.log(LogStatus.PASS,
									"Current and New " + FieldNames[i] + " is displayed in worknotes as " + "Current "
											+ InitialGCPData[i] + " | " + "New " + FieldNames[i] + " - " + arr1[i]);
						} else {
							logger.log(LogStatus.FAIL,
									"Current and New " + FieldNames[i] + " is not displayed in worknotes.");
						}
					}
				}
			} else {
				logger.log(LogStatus.INFO, "Work Note Activity has null data");
			}
			logger.log(LogStatus.PASS, "Test method: Passed ==> validateWorkNotesActivity");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Test methhod: Failed ==> validateWorkNotesActivity");
			logger.log(LogStatus.FAIL, "Test method: Failed ==> validateWorkNotesActivity");
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author sai.v.kotapali
	 */
	@Test
	public void EditabilityoffieldsforrestaffinginListView() {
		ExtentTest logger = extent.startTest(
				"To check editability of fields for Restaffing, Restaffing Modified, ICM/ cancelled in List View",
				"To check editability of fields for Restaffing, Restaffing Modified, ICM/ cancelled in List View");
		try {
			if ((arr1[0].equals("Restaffing")) || arr1[0].equals("Restaffing cancelled")
					|| arr1[0].equals("Restaffing Modified") || arr1[0].equals("Intra Client Movement")
					|| arr1[0].equals("Intra Client Movement cancelled")) {
				logger.log(LogStatus.INFO, "Process Type is " + arr1[0]);
				UserLoginAsFulfiller();
				openTravelPlanTable();
				util.pause(logger, "5");
				util.clickOn(logger, portal.label(driver, "All"));
				util.pause(logger, "5");
				util.selectBoxByValue(logger, nav.dropdown(driver, "Search", ""), "GCP Document ID");
				util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", ""), DocumentID);
				util.pause(logger, "3");
				addColumn(logger, "Process Type");
				addColumn(logger, "Destination State/Province/Canton");
				util.compareTwoStrings(logger,
						nav.getTableCellText(logger, driver, "Destination State/Province/Canton", ""), arr1[3]);

				// EditabilityoffieldsforrestaffinginListView(logger);
				verifyFieldNonEditable(logger, "Process Type");
        		verifyFieldNonEditable(logger, "Destination State/Province/Canton");

			}
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test method: Failed ==> To check editability of fields for GCP Restaffing, Restaffing Modified, Intra Client Movement");
			logger.log(LogStatus.FAIL,
					"Test method: Failed ==> To check editability of fields for GCP Restaffing, Restaffing Modified, Intra Client Movement");
		}

		extent.endTest(logger);
		extent.flush();
	}

	// @author: hermaine.c.t.canania
	public void verifyFieldNonEditable(ExtentTest logger, String fieldName) {
		try
		{
			int i = util.returnColumnIndex(logger, "//table[not(contains(@id,'clone'))]//th/span/i[not(@aria-hidden='true')]/parent::span", fieldName, driver);
			System.out.print(i);
			util.clickOn(logger, driver.findElement(By.xpath("//table[not(contains(@id,'clone'))]//tr//td[contains(@class,'vt')]["+i+"]")));
			driver.findElement(By.xpath("//table[not(contains(@id,'clone'))]//tr//td[contains(@class,'vt')]["+i+"]")).sendKeys(""+Keys.ENTER);
			try
			{
				if(nav.tooltip(driver, "Save (Enter)","","").isDisplayed()){
					logger.log(LogStatus.FAIL, "Field: " + fieldName + " is NOT Read Only");
				}
				else
				{
					logger.log(LogStatus.PASS, "Field: " + fieldName + " is Read Only");
				}
			}
			catch (Exception e)	{
				logger.log(LogStatus.PASS, "Field: " + fieldName + " is Read Only");
			}
			util.clickOn(logger,nav.tooltip(driver, "Cancel (ESC)","","") );
		}
		catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Edit Table Items issue");
		}
	}

	@Parameters({ "CancelledPayload" })
	@Test
	public void validate_HR_TASK_GCP_Restaffing_or_Intra_Client_Movement_cancelled(String CancelledPayload) {
		ExtentTest logger = extent.startTest(
				"Validate HR TASK : GCP Restaffing cancelled or Intra Client Movement cancelled",
				"Validate HR TASK : GCP Restaffing cancelled or Intra Client Movement cancelled");
		try {
			updateExistingGCPRecord();
			openGCPTravelPlanAndVerifyProcessType(logger);
			util.pause(logger, "5");
			util.endofpage(logger);
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			Open_HR_TASK_Restaffing_or_Intra_Client_Movement_cancelled();
			validateGCPHRTaskFieldMappingAndEditability(logger, "PMG GCP Restaffing/ Intra-Client Movement Cancellation",
					"PMG GCP Restaffing/ Intra-Client Movement Cancellation", "T39883.01.fulfiller");

		} catch (Exception e) {
			// TODO: handle exception
		}
	}

	@Test
	public void Open_HR_TASK_Restaffing_or_Intra_Client_Movement_cancelled() {
		ExtentTest logger = extent.startTest("Open HR TASK : Restaffing or Intra Client Movement cancelled",
				"Open HR TASK : Restaffing or Intra Client Movement cancelled");
		try {
			util.pause(logger, "5");
			util.endofpage(logger);
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, "PMG GCP Restaffing/ Intra-Client Movement Cancellation", "Short description", "HR Tasks",
					"Work in Progress");
		} catch (Exception e) {
			// TODO: handle exception
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author k.p.balakrishnan
	 * @param logger
	 * @param HRTaskName
	 * @param ShortDescription
	 * @param TemplateName
	 * @param AssigneeId
	 * @implNote : Use to validate field editablity and field mapping for all GCP HR
	 *           Tasks (common method)
	 */
	@Test
	public void validateGCPHRTaskFieldMappingAndEditability(ExtentTest logger, String ShortDescription,
			String TemplateName, String AssigneeId) {
		try {

			String payload = getInputData(TestName, "Payload2");
			String ProcessType = fetchNewProcessType(payload);

			String FieldsforVerifying[] = { "Number", "Template", "HR Case", "State", "Travel Plan", "GCP Process Type",
					"Assignment group", "Assigned to", "Short description", "Description", "Work notes" };
			for (String field : FieldsforVerifying) {
				util.verifyElementByXpath(logger, nav.label(driver, field, ""));
			}
			String FieldforVerifyingContainsByValue[] = { "Number", "Template", "HR Case", "Travel Plan",
					"GCP Process Type" };
			String ValuesforVerifyingContainsByValue[] = { "HRT", TemplateName, "HRC", TravelPlanNumber, ProcessType };
			for (int i = 0; i < 5; i++) {
				util.verifyTextContainsByValue(logger, nav.text(driver, FieldforVerifyingContainsByValue[i], ""),
						ValuesforVerifyingContainsByValue[i]);
			}
			if (verifySelectedValueInDropdown(driver, "State", "").contains("Work in Progress")) {
				System.out.println("State field value contains Work in Progress");
				logger.log(LogStatus.PASS, "State field value contains Work in Progress");
			} else {
				System.out.println("State field value does not contain Work in Progress");
				logger.log(LogStatus.FAIL, "State field value does not contain Work in Progress");
			}
			String FieldForVerifyingDisabled[] = { "Number", "Template", "HR Case", "Travel Plan", "GCP Process Type",
					"Short description" };
			for (String field : FieldForVerifyingDisabled) {
				util.verifyElementDisabled(logger, nav.text(driver, field, ""));
			}
			util.pause(logger, "2");
			
			Auto_Generated_HR_Task_Number = util.getElementValue(logger, nav.text(driver, "Number", ""));
			Auto_Generated_HR_Case_Number = util.getElementValue(logger, nav.text(driver, "HR Case", ""));

			String FieldForVerifyingEnabled[] = { "Assignment group", "Assigned to", "Work notes" };
			/*for (String field : FieldForVerifyingEnabled) {
				if (nav.text(driver, field, "").isEnabled())
					logger.log(LogStatus.PASS, field + " is enabled");
				else
					logger.log(LogStatus.FAIL, field + " is disabled");
			}*/

			String AssignmentGroup = portal.text(driver, "Assignment group").getAttribute("value");
			logger.log(LogStatus.INFO, "Assignment Group found in HR Task "+ShortDescription+" is: "+AssignmentGroup);	
			if (AssignmentGroup.equalsIgnoreCase(getInputData(TestName, "AssignmentGroup"))) {
				logger.log(LogStatus.PASS, "Assignment Group value is as expected");
			} else {
				logger.log(LogStatus.FAIL, "Assignment Group value is not as expected");
			}
			
			VerifyPopulateAssignedTo(logger, "T39883.02.admin");
			util.compareTwoStrings(logger, util.getElementValue(logger, nav.text(driver, "Short description", "")),
					ShortDescription);
			//util.verifyNullTextByValue(logger, nav.text(driver, "Description", ""));
			//util.setText(logger, nav.text(driver, "Description", ""), getInputData(TestName, "Description"));
			util.verifyNullTextByValue(logger, nav.text(driver, "Work notes", ""));
			util.scrollByVisibleElement(driver, logger, driver.findElement(By.xpath(
					"//*[text()='Work notes']/parent::label/parent::div[not(@aria-hidden='true')]//textarea[@id='activity-stream-textarea']")));
			util.setText(logger, driver.findElement(By.xpath(
					"//*[text()='Work notes']/parent::label/parent::div[not(@aria-hidden='true')]//textarea[@id='activity-stream-textarea']")),
					"For testing. Work notes");
			logger.log(LogStatus.PASS,
					"All fields are correctly populated and have the correct properties in the HR Task: "
							+ ShortDescription);

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Test method failed --> validateGCPHRTaskFieldMappingAndEditability");
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test method failed --> validateGCPHRTaskFieldMappingAndEditability");
		}
		extent.endTest(logger);
		extent.flush();
	}

		/**
	 * @author k.p.balakrishnan
	 * @param logger
	 * @param HRTaskName
	 * @param ShortDescription
	 * @param TemplateName
	 * @param AssigneeId
	 * @implNote : Use to validate field editablity and field mapping for all GCP HR
	 *           Tasks (common method)
	 */
	@Test
	public void validateGCPHRTaskFieldMappingAndEditabilityForPayload3(ExtentTest logger, String ShortDescription,
			String TemplateName, String AssigneeId) {
		try {

			String payload = getInputData(TestName, "Payload3");
			String ProcessType = fetchNewProcessType(payload);

			String FieldsforVerifying[] = { "Number", "Template", "HR Case", "State", "Travel Plan", "GCP Process Type",
					"Assignment group", "Assigned to", "Short description", "Description", "Work notes" };
			for (String field : FieldsforVerifying) {
				util.verifyElementByXpath(logger, nav.label(driver, field, ""));
			}
			String FieldforVerifyingContainsByValue[] = { "Number", "Template", "HR Case", "Travel Plan",
					"GCP Process Type" };
			String ValuesforVerifyingContainsByValue[] = { "HRT", TemplateName, "HRC", TravelPlanNumber, ProcessType };
			for (int i = 0; i < 5; i++) {
				util.verifyTextContainsByValue(logger, nav.text(driver, FieldforVerifyingContainsByValue[i], ""),
						ValuesforVerifyingContainsByValue[i]);
			}
			if (verifySelectedValueInDropdown(driver, "State", "").contains("Work in Progress")) {
				System.out.println("State field value contains Work in Progress");
				logger.log(LogStatus.PASS, "State field value contains Work in Progress");
			} else {
				System.out.println("State field value does not contain Work in Progress");
				logger.log(LogStatus.FAIL, "State field value does not contain Work in Progress");
			}
			String FieldForVerifyingDisabled[] = { "Number", "Template", "HR Case", "Travel Plan", "GCP Process Type",
					"Short description" };
			for (String field : FieldForVerifyingDisabled) {
				util.verifyElementDisabled(logger, nav.text(driver, field, ""));
			}
			util.pause(logger, "2");
			
			Auto_Generated_HR_Task_Number = util.getElementValue(logger, nav.text(driver, "Number", ""));
			Auto_Generated_HR_Case_Number = util.getElementValue(logger, nav.text(driver, "HR Case", ""));

			String FieldForVerifyingEnabled[] = { "Assignment group", "Assigned to", "Work notes" };
			/*for (String field : FieldForVerifyingEnabled) {
				if (nav.text(driver, field, "").isEnabled())
					logger.log(LogStatus.PASS, field + " is enabled");
				else
					logger.log(LogStatus.FAIL, field + " is disabled");
			}*/

			String AssignmentGroup = portal.text(driver, "Assignment group").getAttribute("value");
			logger.log(LogStatus.INFO, "Assignment Group found in HR Task "+ShortDescription+" is: "+AssignmentGroup);	
			if (AssignmentGroup.equalsIgnoreCase(getInputData(TestName, "AssignmentGroup"))) {
				logger.log(LogStatus.PASS, "Assignment Group value is as expected");
			} else {
				logger.log(LogStatus.FAIL, "Assignment Group value is not as expected");
			}
			
			VerifyPopulateAssignedTo(logger, "T39883.02.admin");
			util.compareTwoStrings(logger, util.getElementValue(logger, nav.text(driver, "Short description", "")),
					ShortDescription);
			//util.verifyNullTextByValue(logger, nav.text(driver, "Description", ""));
			//util.setText(logger, nav.text(driver, "Description", ""), getInputData(TestName, "Description"));
			util.verifyNullTextByValue(logger, nav.text(driver, "Work notes", ""));
			util.scrollByVisibleElement(driver, logger, driver.findElement(By.xpath(
					"//*[text()='Work notes']/parent::label/parent::div[not(@aria-hidden='true')]//textarea[@id='activity-stream-textarea']")));
			util.setText(logger, driver.findElement(By.xpath(
					"//*[text()='Work notes']/parent::label/parent::div[not(@aria-hidden='true')]//textarea[@id='activity-stream-textarea']")),
					"For testing. Work notes");
			logger.log(LogStatus.PASS,
					"All fields are correctly populated and have the correct properties in the HR Task: "
							+ ShortDescription);

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Test method failed --> validateGCPHRTaskFieldMappingAndEditability");
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test method failed --> validateGCPHRTaskFieldMappingAndEditability");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// @author: hermaine.c.t.canania
	public static String fetchNewProcessType(String payload) {
        if (payload != null && !payload.isEmpty()) {
            String[] newValues = payload.split(",");
            if (newValues.length > 0) {
                return newValues[0]; // Extract the new Process Type value
            }
        }
        return "";
    }

	// Sreenath
	// Validating Started From field
	@Test
	public void ValidatingStartedFromField() {
		ExtentTest logger = extent.startTest("Verify Started From Field", "Verify Started From Field");
		try {
			addColumn(logger, "Started From");
			util.scrollByVisibleElement(driver, logger, nav.link(driver, "Started From", ""));
			String StartedFrom = nav.getTableCellText(logger, driver, "Started From", "");
			System.out.println("Started From: " + StartedFrom);
			if (StartedFrom.equals("GCP Hub")) {
				logger.log(LogStatus.PASS, "Started From Value In Travel Plan is: " + StartedFrom);
			} else {
				logger.log(LogStatus.FAIL,
						"Started From Value In Travel Plan has Invalid value or updated incorrectly.");
			}
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Test method failed: Validate Started From In GCP Travel Plan");
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test method failed: Validate Started From In GCP Travel Plan");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void openRITMTable() {
		ExtentTest logger = extent.startTest("Open RITM table", "Open RITM table.");
		try {
			browserHelper.navigateTo(logger, URL + "/sc_req_item_list.do?sysparm_clear_stack=true");
			util.pause(logger, "7");
		} catch (Exception e) {
			// TODO: handle exception
		}
	}

	@Test
	public void openCreatedGCP_RITMInFormView() {
		ExtentTest logger = extent.startTest("Open Created GCP RITM In Form View",
				"Open Created GCP RITM In Form View.");
		try {
			util.pause(logger, "3");
			util.clickOn(logger, nav.tooltip(driver, "Preview", "", ""));
			util.pause(logger, "5");
			util.clickOn(logger, nav.link(driver, "Open Record", ""));
			util.pause(logger, "5");
			System.out.println("Record: " + RITM + " is opened");
			logger.log(LogStatus.PASS, "Record: " + RITM + " is opened");
			String Openedby = util.getElementValue(logger, nav.text(driver, "Opened by", ""));
			if (Openedby.contains("richie.a.acuna")) {
				System.out.println("Opened by is richie.a.acuna");
			} else {
				System.out.println("Opened by is mismatched");
			}
			String Requestedfor = util.getElementValue(logger, nav.text(driver, "Requested for", ""));
			if (Requestedfor.contains("richie.a.acuna")) {
				System.out.println("Requested for is richie.a.acuna");
			} else {
				System.out.println(" Requested for is mismatched");
			}
			String Location = util.getElementValue(logger, nav.text(driver, "Location", ""));
			if (Location.contains("Mandaluyong, Robinsons Cybergate Tower 2")) {
				System.out.println("Location is Mandaluyong, Robinsons Cybergate Tower 2");
			} else {
				System.out.println("Location is mismatched");
			}
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Application", ""));
			String Application = util.getElementValue(logger, nav.text(driver, "Application", ""));
			if (Application.contains("GCP (Global Career Program)")) {
				System.out.println("Application is GCP (Global Career Program)");
			} else {
				System.out.println("Application is mismatched");
			}
			String ApplicationWebsiteURL = util.getElementValue(logger,
					nav.text(driver, "Application website/URL", ""));
			if (ApplicationWebsiteURL.contains("gcphub.accenture.com")) {
				System.out.println("ApplicationWebsiteURL is gcphub.accenture.com");
			} else {
				System.out.println("ApplicationWebsiteURL is mismatched");
			}
			String Category = util.getElementValue(logger, nav.text(driver, "Category", ""));
			if (Category.contains("Data Request - Process and Tool functionality mismatch")) {
				System.out.println("Category is Data Request - Process and Tool functionality mismatch");
			} else {
				System.out.println("Category is mismatched");
			}
			String[] GCP15Attributes = { "ProcessType", "EnterpriseID", "EmployeeHostCountry", "EmployeeHostState",
					"EmployeeHostCity", "WorkLocationAddress", "ClientName", "AssignmentStartDate", "FinalGCPEndDttm",
					"ProjectName", "ProjectAccentureLeader", "TravelApprover",
					"ChargeCode", "ProposedVisaType" };
			Des = "For the payload with Document ID " + "'" + DocumentID + "'" + ", " + "mandatory field(s) - ";
			int flag = 0;
			for (int j = 0; j < GCP15Attributes.length; j++) {
				if (getInputData(TestName, GCP15Attributes[j]) == "") {
					if (flag == 1)
						Des += ", ";
					Des += GCP15Attributes[j];
					flag = 1;
				}
			}
			Des += " have null value. Therefore, no travel plan has been created.";
			System.out.println(Des);
			util.compareTwoStrings(logger, nav.text(driver, "Description", "").getAttribute("value"),
					Des);
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Location", ""));
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to open RITM record " + RITM);
			logger.log(LogStatus.FAIL, "Record: " + RITM + " is failed to be opened");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void VerifyingRITM() {
		ExtentTest logger = extent.startTest("Verifying RITM",
				"Verifying RITM Flow");
		try {
			loginAsAdmin();
			util.pause(logger, "30");
			openRITMTable();
			util.clickOn(logger, portal.label(driver, "All"));
			util.pause(logger, "5");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Search", ""), "Description");
			util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", ""), "*" + DocumentID);
			util.pause(logger, "3");
			util.scrollByVisibleElement(driver, logger, nav.link(driver, "Number", ""));
			RITM = nav.getTableCellText(logger, driver, "Number", "");
			System.out.println("RITM: " + RITM);
			logger.log(LogStatus.INFO, RITM);
			util.verifyElementByXpath(logger, nav.tooltip(driver, "Preview RITM", "", ""));
			RITM = nav.tooltip(driver, "Preview RITM", "", "").getAttribute("data-original-title")
					.split(" ")[1].split(":")[0];
			System.out.println("RITM: " + RITM);
			logger.log(LogStatus.INFO, RITM);
			if (RITM.equals(null) || RITM.equals("")) {
				logger.log(LogStatus.FAIL, RITM
						+ "  (RITM number) is failed to fetched whose document ID: " + DocumentID);
			} else {
				logger.log(LogStatus.PASS, TravelPlanNumber
						+ " (RITM number) is fetched and its associate with document ID: " + DocumentID);
			}
		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL,
					RITM + " (RITM number) is failed to fetched whose document ID: " + DocumentID);
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void verifyEmailContentForRITM() throws InterruptedException {
		ExtentTest logger = extent.startTest("RITM mail validation", "RITM mail validation");
		try {
			util.pause(logger, "20");
			String reviewerMailID = "IT Service Desk";
			String requesterMailID = "mobility.applications.supportgroup@accenture.com, gcp.ops.team@accenture.com";
			System.out.println(RITM);
			String emailCont = "you contacted Accenture Support. A new Requested Item has been created.\r\n"
					+ "Here are the details:\r\n"
					+ "Reference Number:  " + RITM + "\r\n"
					+ "Description: " + Des + "\r\n"
					+ "Please go to Accenture Support to review the details of your Requested Item.\r\n";
			// Subject
			String subject = "Requested Item"
					+ RITM + " has been opened";
			util.verifyElementByXpath(logger, portal.label(driver, "Requested Item RITM"));
			System.out.println("0");
			String mailXPath = "//*[contains(text(),'Requested Item RITM')]/../..";
			System.out.println("1");
			String subjectFromPage = driver.findElement(By.xpath(mailXPath + "/li[2]/span[2]")).getText();
			subject = subject.replaceAll(" ", "");
			subjectFromPage = subjectFromPage.replaceAll(" ", "");
			System.out.println("2");
			if (subjectFromPage.contains(subject))
				System.out.println("Subject is verified");
			String mailreviewers = driver.findElement(By.xpath(mailXPath + "/li[3]")).getText();
			if (mailreviewers.contains(reviewerMailID))
				System.out.println("Reviewers are verified");
			String mailRequesters = driver.findElement(By.xpath(mailXPath + "/li[4]")).getText();
			if (mailRequesters.contains(requesterMailID))
				System.out.println("Requesters are verified");
			System.out.println("3");
			// Show email details
			driver.findElement(By.xpath(mailXPath + "/li[5]/span[2]/a")).click();
			driver.switchTo().frame(driver.findElement(By.xpath("//iframe[contains(@class,'card')]")));
			String emailLog = driver.findElement(By.xpath(".//head/base[@target='_blank']//following::body")).getText();
			System.out.println(emailLog);
			emailLog = emailLog.replaceAll("\\s", "");
			System.out.println(emailLog);
			emailCont = emailCont.replaceAll("\\s", "");
			System.out.println("Email Log : \n" + emailLog);
			System.out.println("Email Content : \n" + emailCont);
			if (emailLog.contains(emailCont))
				System.out.println("Email content is verified");
			else
				System.out.println("Email content is not verified");
			driver.navigate().refresh();
			util.pause(logger, "5");
			TASK = nav.getTableCellText(logger, driver, "Assignment group", "Catalog Tasks");
			System.out.println("TASK: " + TASK);
			if (TASK.contains("APPSUP-OPER-CIO-AD-Devl-India-GCP-Tracker")) {
				System.out.println("APPSUP-OPER-CIO-AD-Devl-India-GCP-Tracker & Assignment Group is Matched");
			} else {
				System.out.println("Assignment group is mismatched");
			}
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to Populate Request Form");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// Shaurya
	@Parameters({ "UIAction" })
	@Test
	public void UIActionsOnRestaffingOrICMHRTasks(String UIAction) {
		ExtentTest logger = extent.startTest("UI Actions On Restaffing Or ICM HR Tasks",
				"UI Actions On Restaffing Or ICM HR Tasks");
		try {

			TP1 = TravelPlanNumber;
			UserLoginAsFulfiller();
			OpenTravelPlan(TravelPlanNumber);
			util.pause(logger, "5");

			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, "PMG GCP Restaffing, Modified Restaffing or Intra Client Movement", "Short description", "HR Tasks", "Work in Progress");
			util.pause(logger, "3");

			// Click the button in the Restaffing HR Task
			util.clickOn(logger, nav.button(driver, UIAction, ""));
			util.pause(logger, "20");
		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL, "Eligibility Check For GCP HR Task is not closed");
		}
	}

	@Test
	public void verifyPayloadValuesInTP2IsUpdatedInRestaffingScenario() {
		ExtentTest logger = extent.startTest("verify Payload Values In TP2 Is Updated In Restaffing Scenario",
				"verify Payload Values In TP2 Is Updated In Restaffing Scenario");
		try {
			getTravelPlanNumberFromCreatedGCPTravelPlan();
			openCreatedGCP_TravelPlanInFormView();
			String fields[] = { "Traveler User ID", "Destination Country/Location", "Travel Start Date",
					"Travel End Date", "Street Address if not in office", "Destination Office City",
					"Project Accenture Leader", "Travel Approver", "Client Name", "Project Name", "Charge Code" };
			String fieldValues[] = new String[10];
			util.clickOn(logger, portal.label(driver, "Main Details"));
			for (int i = 0; i < fields.length; i++) {
				for (int j = 0; j < fieldValues.length; j++) {
					// scrollToElementToCenter(portal.label(driver, fields[i]), driver);
					String fieldValue = portal.text(driver, "Travel Start Date").getAttribute("value");
					fieldValues[j] = fieldValue;
				}
			}
			String PayloadValues[] = { EnterpriseID, EmployeeHostCountry, AssignmentStartDate, FinalGCPEndDttm,
					WorkLocationAddress, EmployeeHostCity, ProjectAccentureLeader, TravelApprover, ClientName,
					ProjectName, ChargeCode };
			if (Arrays.equals(PayloadValues, fieldValues)) {
				System.out.println("Payload values are reflected in TP2 correctly");
			}
			scrollToElementToCenter(portal.label(driver, "Project Visa Type"), driver);
			Select s = new Select(portal.dropdown(driver, "Project Visa Type"));
			String projectVisaType = s.getFirstSelectedOption().getText();
			if (projectVisaType.equalsIgnoreCase(ProposedVisaType)) {
				logger.log(LogStatus.PASS, "Project Visa Type in TP2 is same as it was in TP1");
			}
			Editabilityoffieldsforrestaffing();
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Traveler Unable to Cancels GCP Travel Plan in PMG Dashboard");
			util.screenShotAndErrorMsg(logger, e, driver, "Test method failed: TravelerCancelsGCPTravelPlan");
		}
		extent.endTest(logger);
		extent.flush();

	}

	//@author: hermaine.c.t.canania
	//Verify if payload values reflected in newly created travel plan
	@Test
	public void verificationofPayloadValuesInTP2IsUpdatedInRestaffingScenario() {
		ExtentTest logger = extent.startTest("Verify if payload values reflected in newly created travel plan in Restaffing scenario",
				"Verify if payload values reflected in newly created travel plan in Restaffing scenario");
		try {
			
			util.pause(logger, "10");
			String fields[] = { "Traveler User ID", "Destination Country/Location", "Travel Start Date",
                "Travel End Date", "Street Address if not in office", "Project Accenture Leader", "Travel Approver", "Client Name", "Project Name", "Charge Code" };

			// Simulating payload2 values retrieval
			String payloadValues = getInputData(TestName, "Payload");
			String arr[] = payloadValues.split(",");
			String arr1[] = new String[arr.length];
			
			for (int i = 0; i < arr.length; i++) {
				arr1[i] = arr[i];
			}

			for (int i = 0; i < fields.length; i++) {
				try {
					WebElement element = driver.findElement(By.xpath("//*[text()='" + fields[i] + "']/../parent::div/following-sibling::div//input[contains(@style,';')]"));
					String fieldValue = element.getAttribute("value");
					String expectedValue = arr1[i];
	
					if (expectedValue != null && expectedValue.equals(fieldValue)) {
						System.out.println("PASS: " + fields[i] + " matches expected value: " + expectedValue);
					} else {
						System.out.println("FAIL: " + fields[i] + " does not match. Expected: " + expectedValue + ", Found: " + fieldValue);
					}
				} catch (Exception e) {
					System.out.println("ERROR: Could not retrieve value for field: " + fields[i]);
				}
			}

			Editabilityoffieldsforrestaffing();
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Traveler Unable to Cancels GCP Travel Plan in PMG Dashboard");
			util.screenShotAndErrorMsg(logger, e, driver, "Test method failed: TravelerCancelsGCPTravelPlan");
		}
		extent.endTest(logger);
		extent.flush();

	}

	@Test
	public void verifyRestaffingCancellationFunctionalityOnTP2() {
		ExtentTest logger = extent.startTest("verify Restaffing Cancellation Functionality On TP2",
				"verify Restaffing Cancellation Functionality On TP2");
		try {
			updateExistingGCPRecord();	
			OpenTravelPlan(TP2);
			
			util.clickOn(logger, portal.label(driver, "Main Details"));
			if (portal.text(driver, "GCP Document ID").getAttribute("value") == "") {
				logger.log(LogStatus.PASS, "GCP Document ID field is blank");
			}
			
			scrollToElementToCenter(nav.label(driver, "HRC", "HR Cases"), driver);
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, "PMG GCP Restaffing/ Intra-Client Movement Cancellation", "Short description", "HR Tasks", "Work in Progress");

			util.pause(logger, "5");
			ProcessType = "Restaffing cancelled";
			validateGCPHRTaskFieldMappingAndEditability(logger,
					"PMG GCP Restaffing/ Intra-Client Movement Cancellation",
					"PMG GCP Restaffing/ Intra-Client Movement Cancellation", "T39883.01.fulfiller");
			util.verifyElementByXpath(logger, portal.button(driver, "Update"), "Update");
			util.verifyElementByXpath(logger, portal.button(driver, "Close Complete"), "Close Complete");
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Traveler Unable to Cancels GCP Travel Plan in PMG Dashboard");
			util.screenShotAndErrorMsg(logger, e, driver, "Test method failed: TravelerCancelsGCPTravelPlan");
		}
		extent.endTest(logger);
		extent.flush();

	}

	@Test
	public void verifyRestaffingCancellationFunctionalityOnTP1() {
		ExtentTest logger = extent.startTest("verify Restaffing Cancellation Functionality On TP1",
				"verify Restaffing Cancellation Functionality On TP1");
		try {
			UserLoginAsFulfiller();
			OpenTravelPlan(TP1);
			ProcessType = "Restaffing";
			
			Editabilityoffieldsforrestaffing();
			util.clickOn(logger, portal.label(driver, "Main Details"));
			if (portal.text(driver, "GCP Document ID").getAttribute("value") == "") {
				logger.log(LogStatus.PASS, "GCP Document ID field is blank");
			}
			util.pause(logger, "5");
			
			scrollToElementToCenter(nav.label(driver, "HRC", "HR Cases"), driver);
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, "PMG GCP Restaffing/ Intra-Client Movement Cancellation", "Short description", "HR Tasks", "Work in Progress");

			util.pause(logger, "5");
			validateGCPHRTaskFieldMappingAndEditability(logger,
					"PMG GCP Restaffing/ Intra-Client Movement Cancellation",
					"PMG GCP Restaffing/ Intra-Client Movement Cancellation", "T39883.01.fulfiller");
			util.verifyElementByXpath(logger, portal.button(driver, "Update"), "Update");
			util.verifyElementByXpath(logger, portal.button(driver, "Close Complete"), "Close Complete");
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Traveler Unable to Cancels GCP Travel Plan in PMG Dashboard");
			util.screenShotAndErrorMsg(logger, e, driver, "Test method failed: TravelerCancelsGCPTravelPlan");
		}
		extent.endTest(logger);
		extent.flush();

	}

	@Test
	public void completeEligibilitytask() {
		ExtentTest logger = extent.startTest("verify Restaffing Cancellation Functionality On TP1",
				"verify Restaffing Cancellation Functionality On TP1");
		try {

			OpenTravelPlan(TP1);
			
			scrollToElementToCenter(nav.label(driver, "HRC", "HR Cases"), driver);
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, "Eligibility Check for GCP", "Short description", "HR Tasks", "Work in Progress");

			util.pause(logger, "5");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Is Traveler Eligible", ""), "Yes");
			util.clickOn(logger, nav.button(driver, "Close Complete", ""));
			
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Traveler Unable to Cancels GCP Travel Plan in PMG Dashboard");
			util.screenShotAndErrorMsg(logger, e, driver, "Test method failed: TravelerCancelsGCPTravelPlan");
		}
		extent.endTest(logger);
		extent.flush();

	}


	@Test
	public void OpenTravelPlan(String TPNumber) throws AWTException {
		ExtentTest logger = extent.startTest("Open the Travel Plan", "Open the Travel Plan");
		try {
			browserHelper.navigateTo(logger, ADSSNowURL);
			List<String> item = new ArrayList<String>();
			item.add("People Mobility");
			item.add("Travel Plans");
			shadowDomFilterSearch(logger, item.get(0), item, "Travel Plans");
			openRecord(logger, TPNumber, "Number");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to Open the IRW Table");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void gcpTravelplanUpdation() {
		ExtentTest logger = extent.startTest("Verify Updation of Process Types", "Verify Updation of Process Types");
		try {

			PostGCPCallUsingExistingDocId("Payload3");
			util.pause(logger, "35");

			getTravelPlanNumberFromCreatedGCPTravelPlan();
			openCreatedGCP_TravelPlanInFormView();

			ProcessType = getInputData(TestName, "ProcessType");
			EnterpriseID = getInputData(TestName, "EnterpriseID");
			EmployeeHostCountry = getInputData(TestName, "EmployeeHostCountry");
			EmployeeHostState = getInputData(TestName, "EmployeeHostState");
			EmployeeHostCity = getInputData(TestName, "EmployeeHostCity");
			WorkLocationAddress = getInputData(TestName, "WorkLocationAddress");
			ClientName = getInputData(TestName, "ClientName");
			AssignmentStartDate = getInputData(TestName, "AssignmentStartDate");
			FinalGCPEndDttm = getInputData(TestName, "FinalGCPEndDttm");
			ProjectName = getInputData(TestName, "ProjectName");
			ProjectAccentureLeader = getInputData(TestName, "ProjectAccentureLeader");
			TravelApprover = getInputData(TestName, "TravelApprover");
			ChargeCode = getInputData(TestName, "ChargeCode");
			ProposedVisaType = getInputData(TestName, "ProposedVisaType");

			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Activities"));
			util.clickOn(logger, portal.label(driver, "Activities"));

			String fieldNames[] = { "Process Type", "Traveler User ID", "Destination Country/Location",
					"Destination State/Province/Canton", "Destination Office City",
					"Street Address if not in office", "Client Name", "Travel Start Date",
					"Travel End Date", "Project Name", "Project Accenture Leader", "Travel Approver",
					"Charge Code", "Project Visa Type" };
			String newValues[];
			String existingValues[] = { ProcessType, EnterpriseID, EmployeeHostCountry, EmployeeHostState,
					EmployeeHostCity,
					WorkLocationAddress, ClientName, AssignmentStartDate, FinalGCPEndDttm, ProjectName,
					ProjectAccentureLeader, TravelApprover, ChargeCode, ProposedVisaType };

			String payloadValues = getInputData(TestName, "Payload3");
			newValues = payloadValues.split(",");

			System.out.println("------------------------------------------------------------------------");
			System.out.println("Changes for " + newValues[0] + " : ");
			for (int i = 0; i < fieldNames.length; i++) {
				if (fieldNames[i].contains("Charge Code") || (fieldNames[i].contains("Project Visa Type"))
						|| (fieldNames[i].contains("Traveler User ID")
								|| (fieldNames[i].contains("Destination Country/Location")))) {
					System.out.println(fieldNames[i] + " value ");
					System.out.println("Existing value: " + existingValues[i]);
					System.out.println("New value     : " + newValues[i]);
					System.out.println(fieldNames[i] + " changes will not be updated.");
					logger.log(LogStatus.PASS, fieldNames[i] + " changes will not be updated. " + "Existing value: "
							+ existingValues[i] + " New value: " + newValues[i]);
				} else if (newValues[i].equals(existingValues[i])) {
					System.out.println(fieldNames[i] + " has no change in value");
					logger.log(LogStatus.PASS, fieldNames[i] + " has no change in value");
				} else {
					System.out.println(fieldNames[i] + " value is updated");
					System.out.println("Existing value: " + existingValues[i]);
					System.out.println("New value     : " + newValues[i]);
					logger.log(LogStatus.PASS, fieldNames[i] + " value is updated. " + "Existing value: "
							+ existingValues[i] + "New value: " + newValues[i]);
					verifyFieldsInActivitiesTab(logger, fieldNames[i], existingValues[i], newValues[i]);
					existingValues[i] = newValues[i];
				}
			}

			util.pause(logger, "5");
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Search", "HR Tasks"), "Short description");
			util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", "HR Tasks"),
					"Auto-updates from GCP Hub");
			util.clickOn(logger, nav.tooltip(driver, "Preview", "", "HR Tasks"));
			util.pause(logger, "11");
			util.clickOn(logger, nav.link(driver, "Open Record", ""));
			util.pause(logger, "5");
			util.pause(logger, "15");
			validateGCPHRTaskFieldMappingAndEditability(logger, "PMG GCP Reinstatement",
					"PMG GCP Reinstatement", "T39377.01");

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to Verify Updation of Process Types");
			util.screenShotAndErrorMsg(logger, e, driver, "Verify Updation of Process Types");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// Shaurya
	@Test
	public void PMGGCPReinstatementVerification() {
		ExtentTest logger = extent.startTest("UI Actions On Restaffing Or ICM HR Tasks",
				"UI Actions On Restaffing Or ICM HR Tasks");
		try {
			
			updateExistingGCPRecord();
			UserLoginAsFulfiller();
			OpenTravelPlan();
			verifyEditabilityOfFieldsAfterReopeningTP();
		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL, "PMG GCP Reinstatement verification is not done");
		}
	}

	@Test
	public void verifyEditabilityOfFieldsAfterReopeningTP() {
		ExtentTest logger = extent.startTest("verify Editability Of Fields After Reopening TP",
				"verify Editability Of Fields After Reopening TP");
		try {
			util.clickOn(logger, nav.tabName(driver, "Main Details"));
			scrollToElementToCenter(nav.label(driver, "GCP Document ID", ""), driver);
			CheckIfFieldIsAutoPopulatedAndDisabled(logger, nav.text(driver, "GCP Document ID", ""), "GCP Document ID");

			String[] arr = { "Travel Start Date", "Travel End Date", "Street Address if not in office", "Client Name",
					"Project Name", "Charge Code", "Project Accenture Leader", "Travel Approver" };
			for (String str : arr) {
				util.scrollByVisibleElement(driver, logger, nav.label(driver, str, "Main Details"));
				util.isEnabled(logger, nav.text(driver, str, "Main Details"));
				util.pause(logger, "1");
			}
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Main Details"));
			util.clickOn(logger, portal.label(driver, "Main Details"));
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Traveler User ID", ""));
			util.verifyElementDisabled(logger, nav.text(driver, "Traveler User ID", ""));
			util.pause(logger, "1");

			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Destination Country/Location", ""));
			util.verifyElementDisabled(logger, nav.text(driver, "Destination Country/Location", ""));
			util.pause(logger, "1");
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Project Visa Type", "Main Details"));
			util.isEnabled(logger, nav.text(driver, "Project Visa Type", "Main Details"));
			util.pause(logger, "1");

			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Destination Office City", "Main Details"));
			util.isEnabled(logger, nav.text(driver, "Destination Office City", "Main Details"));
			util.pause(logger, "1");

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Traveler Unable to Cancels GCP Travel Plan in PMG Dashboard");
			util.screenShotAndErrorMsg(logger, e, driver, "Test method failed: TravelerCancelsGCPTravelPlan");
		}
		extent.endTest(logger);
		extent.flush();

	}

	// shaurya
	@Parameters({ "Type" })
	@Test
	public void verifyNotification(String Type) throws InterruptedException, AWTException {
		ExtentTest logger = extent.startTest("Verify Notification: " + Type, "Verify Notification: " + Type);
		switch (Type) {
			case "Approver":
				loginAsAdmin();
				OpenTravelPlan();
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
				nav.tabName(driver, "Approvals").click();
				util.pause(logger, "2");
				util.clickOn(logger, nav.tooltip(driver, "Preview", "", "Approvals"));
				util.pause(logger, "11");
				util.clickOn(logger, nav.link(driver, "Open Record", ""));
				util.pause(logger, "5");
				toMailID = getInputData(TestName, "ApproverEID");
				String[] toMail = toMailID.split("@");
				toMailID = toMail[0] + "@email.com";
				fromMailID = "PMGateway@accenturesupport.accenture.com";
				subject = "Action Required: Travel approver request";
				emailCont = "***Confidential - For Company Internal Use Only***  \n" + "Dear ,\n"
						+ "You’ve been selected as travel approver by for their upcoming travel plan ("
						+ TravelPlanNumber
						+ "). Click here to approve, deny or to reassign this request.\n"
						+ "Please visit the Mobility help site for more information about being a traveler approver.\n"
						+ "This is a system-generated email. Here’s how to contact us.\n" + "Best wishes,\n"
						+ "Mobility \n"
						+ "Notice: This message is for the designated recipient only and may contain privileged, proprietary or otherwise confidential information. If you have received it in error, please notify the sender immediately and delete the original. Any other use of the e-mail by you is prohibited.";
				break;

			case "PMGHRTask":
			loginAsAdmin();
			OpenTravelPlan();
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Related Links", ""));
			util.pause(logger, "2");
			nav.tabName(driver, "Tasks").click();
				util.pause(logger, "3");
				util.clickOn(logger, nav.tooltip(driver, "Preview","People Mobility Confirmation", "HR Tasks"));
				util.pause(logger, "11");
				util.clickOn(logger, nav.link(driver, "Open Record", ""));
				util.pause(logger, "5");
				toMailID = getInputData(TestName, "EnterpriseID") + "@email.com";
				fromMailID = "PMGateway@accenturesupport.accenture.com";
				subject = "Action needed for your travel plan";
				emailCont = "***Confidential - For Company Internal Use Only***  \n" + "Dear ,\n" + "Your travel plan ("
						+ TravelPlanNumber + ") has been approved.\n"
						+ "We suggest you check your dashboard regularly. The dashboard contains important status updates, action items and documentation\n"
						+ "related to your travel plans.\n"
						+ "This is a system-generated email. Here’s how to contact us.\n" + "Best wishes, \n"
						+ "Mobility \n"
						+ "Notice: This message is for the designated recipient only and may contain privileged, proprietary or otherwise confidential information. If \n"
						+ "you have received it in error, please notify the sender immediately and delete the original. Any other use of the e-mail by you is prohibited. \n";
				break;
		}

		verifyEmailContent(logger, toMailID, fromMailID, subject, emailCont);
	}

	@Test
	public void verifyEmailContent(ExtentTest logger, String toMailID, String fromMailID, String subject,
			String emailCont) throws InterruptedException {
		util.verifyElementByXpath(logger, portal.label(driver, subject), subject);
		String mailXPath = "//*[contains(text(),'" + subject + "')]/../..";
		String subjectFromPage = driver.findElement(By.xpath(mailXPath + "/li[2]/span[2]")).getText();
		if (subjectFromPage.contains(subject)) {
			logger.log(LogStatus.PASS, "Subject is verified");
		} else {

			logger.log(LogStatus.FAIL, "Subject is not verified");
		}

		String fromMails = driver.findElement(By.xpath(mailXPath + "/li[3]")).getText();
		if (fromMails.contains(fromMailID)) {

			logger.log(LogStatus.PASS, "From field is verified");
		} else {

			logger.log(LogStatus.FAIL, "From field is not verified");
		}

		String toMails = driver.findElement(By.xpath(mailXPath + "/li[4]")).getText();
		if (toMails.contains(toMailID)) {

			logger.log(LogStatus.PASS, "To field is verified");
		} else {

			logger.log(LogStatus.FAIL, "To field is not verified");
		}

		// Show email details
		util.scrollByVisibleElement(driver, logger, nav.link(driver, "Show email details", ""));
		util.clickOn(logger, nav.link(driver, "Show email details", ""));

		util.pause(logger, "15");
		driver.switchTo().frame(driver.findElement(By.xpath(mailXPath + "/../../../div[4]//div/iframe")));

		String emailLog = driver.findElement(By.xpath(".//head/base[@target='_blank']//following::body")).getText();

		emailLog = emailLog.replaceAll("Ref:MSG\\d+", "");
		emailLog = emailLog.replaceAll("\\s", "");
		emailCont = emailCont.replaceAll("Ref:MSG\\d+", "");
		emailCont = emailCont.replaceAll("\\s", "");
		System.out.println(emailLog);
		System.out.println(emailCont);
		util.compareTwoStrings(logger, emailLog, emailCont);

		if (emailLog.contains(emailCont)) {
			logger.log(LogStatus.PASS, "Email content is verified");
			try {
				screenShotAndInfoMsg(logger, driver, "Email content");
			} catch (IOException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
		} else {
			logger.log(LogStatus.FAIL, "Email content is not verified");
		}

	}

	@Test
	public void verifyNotificationOnPMGHRTask() throws InterruptedException, AWTException {
		verifyNotification("PMGHRTask");

	}

	@Test
	public void verifyAutoCancellationOfTP() {
		ExtentTest logger = extent.startTest("verify Restaffing Cancellation Functionality On TP1",
				"verify Restaffing Cancellation Functionality On TP1");
		try {
			driver.navigate().refresh();
			util.pause(logger, "10");
			JavascriptExecutor jse = (JavascriptExecutor) driver;
			WebElement frame = (WebElement) jse.executeScript(
					"return document.querySelector('macroponent-f51912f4c700201072b211d4d8c26010').shadowRoot.querySelector('iframe#gsft_main')");
			util.pause(logger, "3");
			System.out.println("Switch frame done " + driver.switchTo().frame(frame));
			util.pause(logger, "3");
			util.verifyElementDisabled(logger, portal.dropdown(driver, "Status"));
			util.clickOn(logger, portal.label(driver, "Activities"));
			String[] fieldName = { "Activity Comments", "Stage", "State", "Status" };
			String[] changedValue = { "GCP Travel Plan has been auto-cancelled.", "Travel Request Cancelled", "Closed",
					"Cancelled" };
			for (int i = 0; i < 4; i++) {
				verifyFieldsInActivitiesSection(logger, fieldName[i], changedValue[i]);
			}
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Auto Cancellation cannot be verified");
			util.screenShotAndErrorMsg(logger, e, driver, "Auto Cancellation cannot be verified");
		}
		extent.endTest(logger);
		extent.flush();

	}

	@Test
	public void verifyTravelApprovalFlowNotTriggeredInNonH1BFlow() {
		ExtentTest logger = extent.startTest("verify Travel Approval Flow Not Triggered In Non H1B Flow",
				"verify Travel Approval Flow Not Triggered In Non H1B Flow");
		try {
			loginAsAdmin();
			OpenTravelPlan();
			verifyStatusAndStageOfTravelPlan("Travel Request", "People Mobility Review");
			Select select2 = new Select(portal.dropdown(driver, "Stage"));
			WebElement option2 = select2.getFirstSelectedOption();
			System.out.println(option2.getText());
			if (option2.getText().equalsIgnoreCase("People Mobility Review")) {
				logger.log(LogStatus.PASS,
						"Approval stage is skipped and TP directly goes to People mobility review stage");
			} else {
				logger.log(LogStatus.FAIL,
						"Approval stage is skipped and TP directly goes to People mobility review stage");
			}
		//	CloseHRTask("ConfirmTravelRequest");	
			CloseSpecificHRTask("ConfirmTravelRequest","dropdown","People Mobility Confirmation");
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Auto Cancellation cannot be verified");
			util.screenShotAndErrorMsg(logger, e, driver, "Auto Cancellation cannot be verified");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// Garima
	public void date_change_three_days() {
		ExtentTest logger = extent.startTest("verify date change 3 days", "verify date change 3 days");
		try {
			browserHelper.navigateTo(logger, ADSSNowURL);
			List<String> item = new ArrayList<String>();
			item.add("People Mobility");
			item.add("Travel Plans");
			shadowDomFilterSearch(logger, item.get(0), item, "Travel Plans");
			openRecord(logger, TravelPlanNumber, "Number");

			util.clickOn(logger, nav.tabName(driver, "Main Details"));
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Created", ""));
			util.pause(logger, "5");
			util.waitTillElementIsVisible(logger, driver, nav.label(driver, "Created", ""));

			changeValueInJavaScriptPopUp(logger, nav.text(driver, "Created", ""), "sys_created_on", -3);

			util.pause(logger, "5");

			Calendar calendar = Calendar.getInstance();
			calendar.add(Calendar.DAY_OF_YEAR, -3);
			Date pastDateTime = calendar.getTime();
			System.out.println(pastDateTime);
			String dateFormat = "yyyy-MM-dd hh:mm:ss";
			SimpleDateFormat objSDF = new SimpleDateFormat(dateFormat); // Date format string is passed as an argument
																		// to the Date format object
			String pastDateTimeFormatted = objSDF.format(pastDateTime);
			System.out.println(pastDateTimeFormatted);

			// Separating day alone
			String[] parts = pastDateTimeFormatted.split(" ");
			String[] dateParts = parts[0].split("-");
			String dayAlone = dateParts[2].replaceFirst("^0+(?!$)", "");
			System.out.println(dayAlone);

			util.verifyElementByXpath(logger, portal.label(driver, "Approvals ("));
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Approvals ("));
			util.clickOn(logger, driver.findElement(By.xpath("//*[@id='tabs2_list']/span[8]/span/span[2]")));

			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Created", ""));
			util.pause(logger, "5");
			util.waitTillElementIsVisible(logger, driver, nav.label(driver, "Created", ""));

			// int i = util.returnColumnIndex(logger, "//*[@name='approver']/..", "Created",
			// driver);
			int i = util.returnColumnIndex(logger, "//*[@name='approver']/../th", "Created", driver);
			System.out.println(i);

			WebElement we = driver.findElement(By.xpath(
					"//*[contains(@id,'row_u_travel_plan')]/td[" + i + "]/div[contains(@data-original-title,'ago')]"));
			util.clickOn(logger, we);
			// we.sendKeys(Keys.ENTER);
			Actions act = new Actions(driver);
			act.doubleClick(we).build().perform();

			util.pause(logger, "5");

			// pick date and press enter
			// util.clickOn(logger, driver
			// .findElement(By.xpath("//*[contains(@id,'GwtDateTimePicker_day')][text()='" +
			// dayAlone + "']")));

			List<WebElement> mul = driver
					.findElements(By.xpath("//*[contains(@id,'GwtDateTimePicker_day')][text()='" + dayAlone + "']"));
			WebElement e = mul.get(0);
			if(mul.size()>0)
			System.out.println("More than one element present +" );
			System.out.println(e);
			//util.clickOn(logger, e);
			util.clickOn(logger, driver
					.findElement(By.xpath("//*[contains(@id,'GwtDateTimePicker_day')][text()='" + dayAlone + "']")));
			util.clickOn(logger, nav.button(driver, "Save (Enter)", ""));
			util.pause(logger, "5");

			util.pause(logger, "5");

			driver.navigate().back();
			util.waitForPageToLoadCompletely(logger, driver);
			driver.navigate().refresh();
			util.waitForPageToLoadCompletely(logger, driver);

			List<String> item2 = new ArrayList<String>();
			item2.add("System Definition");
			item2.add("Scheduled Jobs");
			shadowDomFilterSearch(logger, item2.get(0), item2, "Scheduled Jobs");

			openRecord(logger, "PMG Approval Remainder Days", "Name");
			util.clickOn(logger, nav.button(driver, "Execute Now", ""));
			util.pause(logger, "5");

		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "unable to verify date change 3 days");
		}

	}

	@Test
	public void date_change_seven_days() {
		ExtentTest logger = extent.startTest("verify date change 7 days",
				"verify date change 7 days");
		try {
			browserHelper.navigateTo(logger, ADSSNowURL);
			List<String> item = new ArrayList<String>();
			item.add("People Mobility");
			item.add("Travel Plans");
			shadowDomFilterSearch(logger, item.get(0), item, "Travel Plans");
			openRecord(logger, TravelPlanNumber, "Number");

			util.clickOn(logger, nav.tabName(driver, "Main Details"));
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Created", ""));
			util.pause(logger, "5");
			util.waitTillElementIsVisible(logger, driver, nav.label(driver, "Created", ""));

			changeValueInJavaScriptPopUp(logger, nav.text(driver, "Created", ""), "sys_created_on", -7);

			util.pause(logger, "5");

			Calendar calendar = Calendar.getInstance();
			calendar.add(Calendar.DAY_OF_YEAR, -7);
			Date pastDateTime = calendar.getTime();
			System.out.println(pastDateTime);
			String dateFormat = "yyyy-MM-dd hh:mm:ss";
			SimpleDateFormat objSDF = new SimpleDateFormat(dateFormat); // Date format string is passed as an argument
																		// to the Date format object
			String pastDateTimeFormatted = objSDF.format(pastDateTime);
			System.out.println(pastDateTimeFormatted);

			// Separating day alone
			String[] parts = pastDateTimeFormatted.split(" ");
			String[] dateParts = parts[0].split("-");
			String dayAlone = dateParts[2].replaceFirst("^0+(?!$)", "");
			System.out.println(dayAlone);

			// String date = pastDateTimeFormatted.substring(7,9);
			// System.out.println(date);

			util.verifyElementByXpath(logger, portal.label(driver, "Approvals ("));
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Approvals ("));
			util.clickOn(logger, driver.findElement(By.xpath("//*[@id='tabs2_list']/span[8]/span/span[2]")));

			util.scrollByVisibleElement(driver, logger, nav.label(driver, "Created", ""));
			util.pause(logger, "5");
			util.waitTillElementIsVisible(logger, driver, nav.label(driver, "Created", ""));

			// int i = util.returnColumnIndex(logger, "//*[@name='approver']/..", "Created",
			// driver);
			int i = util.returnColumnIndex(logger, "//*[@name='approver']/../th", "Created", driver);
			System.out.println(i);

			WebElement we = driver.findElement(By.xpath(
					"//*[contains(@id,'row_u_travel_plan')]/td[" + i + "]/div[contains(@data-original-title,'ago')]"));
			util.clickOn(logger, we);
			// we.sendKeys(Keys.ENTER);
			Actions act = new Actions(driver);
			act.doubleClick(we).build().perform();

			util.pause(logger, "5");

			// pick date and press enter
			// util.clickOn(logger, driver
			// .findElement(By.xpath("//*[contains(@id,'GwtDateTimePicker_day')][text()='" +
			// dayAlone + "']")));
			List<WebElement> mul = driver
					.findElements(By.xpath("//*[contains(@id,'GwtDateTimePicker_day')][text()='" + dayAlone + "']"));
			WebElement e = mul.get(0);
			util.clickOn(logger, e);
			util.clickOn(logger, nav.button(driver, "Save (Enter)", ""));
			util.pause(logger, "5");

			util.pause(logger, "5");

			driver.navigate().back();
			util.waitForPageToLoadCompletely(logger, driver);
			driver.navigate().refresh();
			util.waitForPageToLoadCompletely(logger, driver);

			List<String> item2 = new ArrayList<String>();
			item2.add("System Definition");
			item2.add("Scheduled Jobs");
			shadowDomFilterSearch(logger, item2.get(0), item2, "Scheduled Jobs");

			openRecord(logger, "PMG Approval Remainder Days", "Name");
			util.clickOn(logger, nav.button(driver, "Execute Now", ""));
			util.pause(logger, "5");

		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "unable to verify date change 3 days");
		}
	}

	// This method is used to log-out in the new UI at backend of SN
	@Test
	public void UserlogOut() {
		ExtentTest logger = extent.startTest("User log-out", "User log-out");
		try {
			frameHelper.switchToDefaultFrame(logger, driver);
			util.pause(logger, "30");
			JavascriptExecutor jse = (JavascriptExecutor) driver;
			WebElement avatar = (WebElement) jse.executeScript(
					"return document.querySelector('macroponent-f51912f4c700201072b211d4d8c26010').shadowRoot.querySelector('sn-polaris-layout').shadowRoot.querySelector('sn-polaris-header').shadowRoot.querySelector('div > now-avatar').shadowRoot.querySelector('span > span > span > span.now-line-height-crop')");
			util.clickOn(logger, avatar);
			util.pause(logger, "2");
			WebElement logOut = (WebElement) jse.executeScript(
					"return document.querySelector(\"body > macroponent-f51912f4c700201072b211d4d8c26010\").shadowRoot.querySelector(\"div > sn-canvas-appshell-root > sn-canvas-appshell-layout > sn-polaris-layout\").shadowRoot.querySelector(\"div.sn-polaris-layout.polaris-enabled > div.layout-main > div.header-bar > sn-polaris-header\").shadowRoot.querySelector(\"#userMenu > span > span:nth-child(2) > div > div.user-menu-footer > button > div\")");
			util.clickByJavascriptExecutor(logger, driver, logOut);
			util.pause(logger, "8");
			util.acceptAlertIfAny(logger, driver);
			util.pause(logger, "2");
			util.acceptAlertIfAny(logger, driver);
			util.pause(logger, "2");

			logger.log(LogStatus.PASS, "User logged off successfully");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Test method: userLogOut fails.");
			logger.log(LogStatus.FAIL, "Test method: userLogOut fails.");
		}
		extent.endTest(logger);
		extent.flush();

	}

	@Test
	public void closeRestaffingHrTaskAndCheckForApprovalNotification() {
		ExtentTest logger = extent.startTest("Close Restaffing HR Task", "Close Restaffing HR Task");
		try {
			TP1 = TravelPlanNumber;

			loginAsAdmin();
			util.pause(logger, "5");
			OpenTravelPlan();
			util.pause(logger, "5");

			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");

			if (driver.findElements(By.xpath(
					"//*[text()='HR Tasks']/following::table/tbody//tr/td[text()='PMG GCP Restaffing, Modified Restaffing or Intra Client Movement']"))
					.size() > 0) {
				logger.log(LogStatus.PASS, "Restaffing HR task is displayed");
			}
			util.clickOn(logger, driver.findElement(By.xpath(
					"//*[text()='HR Tasks']/following::table/tbody//tr/td[text()='PMG GCP Restaffing, Modified Restaffing or Intra Client Movement']/parent::tr/td/a[contains(text(),'HRT')]")));
			util.pause(logger, "5");
			util.clickOn(logger, nav.button(driver, "Create New TP and Close Complete", ""));
			util.pause(logger, "5");

			openTravelPlanTable();

			util.clickOn(logger, portal.label(driver, "All"));
			util.pause(logger, "5");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Search", ""), "GCP Document ID");
			util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", ""), DocumentID);
			util.pause(logger, "3");

			util.scrollByVisibleElement(driver, logger, nav.link(driver, "Number", ""));
			TravelPlanNumber = nav.getTableCellText(logger, driver, "Number", "");
			System.out.println("TravelPlanNumber: " + TravelPlanNumber);
			logger.log(LogStatus.INFO, TravelPlanNumber);
			util.verifyElementByXpath(logger, nav.tooltip(driver, "Preview TRA", "", ""));
			TravelPlanNumber = nav.tooltip(driver, "Preview TRA", "", "").getAttribute("data-original-title")
					.split(" ")[1].split(":")[0];
			System.out.println("TravelPlanNumber: " + TravelPlanNumber);
			logger.log(LogStatus.INFO, TravelPlanNumber);
			if (TravelPlanNumber.equals(null) || TravelPlanNumber.equals("")) {
				logger.log(LogStatus.FAIL, TravelPlanNumber
						+ "  (Travel plan number) is failed to fetched whose document ID: " + DocumentID);
			} else {
				logger.log(LogStatus.PASS, TravelPlanNumber
						+ " (Travel plan number) is fetched and its associate with document ID: " + DocumentID);
			}

		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL,
					"Fail to verify deletion of Old GCP Document ID field and addition of GCP Document ID & Parent Travel Plan fields ");
		}
	}

	// Garima
	@Parameters({ "reminder_type" })
	@Test
	public void ApprovalNotificationForRestaffingAndRestaffingModified(String reminder_type) {
		ExtentTest logger = extent.startTest("Approval Notification", "Approval Notification");
		try {
			/*
			 * reminder_type -
			 * for inital reminder notification :Approver
			 * for day 3 & 7 reminder :ReminderToApprover
			 */
			loginAsAdmin();
			util.pause(logger, "5");
			OpenTravelPlan();
			util.pause(logger, "5");
			// util.verifyElementByXpath(logger, nav.label(driver, "Approvals", ""));
			// util.pause(logger, "5");
			// util.clickOn(logger, nav.tooltip(driver, "Preview", "", "Approvals"));
			// util.pause(logger, "3");
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Approvals").click();
			util.pause(logger, "2");
			util.clickOn(logger, nav.tooltip(driver, "Preview", "", "Approvals"));
			util.pause(logger, "11");
			util.clickOn(logger, nav.link(driver, "Open Record", ""));
			// util.waitTillElementIsClickable(logger, driver, nav.link(driver, "Open
			// Record", ""));
			verifyNotificationForApprover(reminder_type);

		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Failed");
			logger.log(LogStatus.FAIL, "Not verified");
		}
		extent.endTest(logger);
	}

	@Parameters({ "Type" })
	@Test
	public void verifyNotificationForApprover(String Type) throws InterruptedException {
		ExtentTest logger = extent.startTest("Verify Notification", "Verify Notification");
		try {
			System.out.println("Cases");
			//TravelPlanNumber = "TRA0825166";
			System.out.println("TravelPlanNumber: " + TravelPlanNumber);
			toMailID = getInputData(TestName, "TravelApprover") + "@email.com";
			System.out.println("toMailID: " + toMailID);

			fromMailID = "PMGateway@accenturesupport.accenture.com";
			CcMailID = getInputData(TestName, "TravelerEID"); // T39377.11@ds.dev.accenture.com
			String[] CcMail2 = CcMailID.split("@");
			CcMailID = CcMail2[0] + "@email.com";

			switch (Type) {
				case "Approver":
					System.out.println("1213123");
					subject = "Action Required: Travel approver request";
					emailCont = "***Confidential - For Company Internal Use Only***\r\n" + "\r\n" + "Dear ,\r\n"
							+ "\r\n"
							+ "You’ve been selected as travel approver by for their upcoming travel plan("
							+ TravelPlanNumber + ")."
							+ " Click here to approve, deny or to reassign this request."
							+ "\r\n"
							+ "Please visit the Mobility help site for more information about being a traveler approver."
							+ "\r\n"
							+ "This is a system-generated email. Here’s how to contact us."
							+ "\r\n"
							+ "Best wishes,\r\n" + "Mobility\r\n"
							+ "Notice: This message is for the designated recipient only and may contain privileged, proprietary "
							+ "or otherwise confidential information. If you have received it in error, please notify the sender "
							+ "immediately and delete the original. Any other use of the e-mail by you is prohibited.\r\n"
							+ "";
					verifyEmailContent(logger, toMailID, fromMailID, subject, emailCont);
					// verifyEmailContent(logger, toMailID, fromMailID, subject, emailCont,
					// CcMailID);
					break;
				case "ReminderToApprover":
					System.out.println("000000");
					subject = "Reminder: Travel approver request";
					emailCont = "***Confidential - For Company Internal Use Only***\r\n" + "\r\n" + "Dear ,\r\n"
							+ "\r\n"
							+ "You’ve been selected as travel approver by for their upcoming travel plan("
							+ TravelPlanNumber + ")."
							+ " Click here to approve, deny or to reassign this request."
							+ "\r\n"
							+ "Please visit the Mobility help site for more information about being a traveler approver."
							+ "\r\n"
							+ "This is a system-generated email. Here’s how to contact us."
							+ "\r\n"
							+ "Best wishes,\r\n" + "Mobility\r\n"
							+ "Notice: This message is for the designated recipient only and may contain privileged, proprietary "
							+ "or otherwise confidential information. If you have received it in error, please notify the sender "
							+ "immediately and delete the original. Any other use of the e-mail by you is prohibited.\r\n"
							+ "";
					// verifyEmailContent(logger, toMailID, fromMailID, subject, emailCont,
					// CcMailID);
					verifyEmailContent(logger, toMailID, fromMailID, subject, emailCont);
					break;

			}
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Failed");
			logger.log(LogStatus.FAIL, "Not verified");
		}
		extent.endTest(logger);
	}

	// Kamal
	@SuppressWarnings("unused")
	@Test
	public void validate_Updated_Values_In_Travel_Plan__From_GCP_Restaffing_RestaffingModified_IntraClientMovement_HR_TASK() {
		ExtentTest logger = extent.startTest("Validate Updated Values in GCP Travel Plan",
				"validate updated values from 'GCP Restaffing Restaffing Modified Intra Client Movement' HR Task");
		try {
			// Verify Travel plan number Whether redirection is successful or not.
			util.verifyElementByXpath(logger, nav.label(driver, "Number", ""));
			String GCP_Travel_Plan_URL = driver.getCurrentUrl();
			logger.log(LogStatus.INFO, "Current GCP Travel plan URL: " + GCP_Travel_Plan_URL);
			// String ActualTravelPlan = util.getElementText(logger, nav.text(driver,
			// "Number", ""));// util.getElementValue(logger, nav.text(driver, "Number",
			// ""));
			// logger.log(LogStatus.INFO, "Redirected Current GCP Travel plan Number:
			// "+ActualTravelPlan);
			if (GCP_Travel_Plan_URL.contains(Sys_ID_of_GCP_TP)) { // && ActualTravelPlan.contains(TravelPlanNumber)
				logger.log(LogStatus.PASS,
						"Successfully redirected to Travel plan form view from 'GCP Restaffing Restaffing Modified Intra Client Movement' HR Task");
				AssignmentStartDate = AssignmentStartDate.split("T")[0];
				FinalGCPEndDttm = FinalGCPEndDttm.split("T")[0];
				arr1[7] = arr1[7].split("T")[0];
				arr1[8] = arr1[8].split("T")[0];
				System.out.println(AssignmentStartDate.split("T")[0]);
				System.out.println(FinalGCPEndDttm.split("T")[0]);
				String[] InitialGCPData = { ProcessType, EnterpriseID, EmployeeHostCountry, EmployeeHostState,
						EmployeeHostCity, WorkLocationAddress, ClientName, AssignmentStartDate, FinalGCPEndDttm,
						ProjectName, ProjectAccentureLeader, TravelApprover, ChargeCode, ProposedVisaType };
				String[] FieldNames = { "", "Traveler User ID", "Destination Country/Location",
						"Destination State/Province/Canton", "Destination Office City",
						"Street Address if not in office", "Client Name", "Travel Start Date", "Travel End Date",
						"Project Name", "Project Accenture Leader", "Travel Approver", "Charge Code", "" };
				String[] TabNames = { "", "", "", "", "Main Details", "Main Details", "Main Details", "Main Details",
						"Main Details", "Main Details", "Main Details", "Main Details", "Main Details", "" };

				for (int i = 1; i < arr1.length - 2; i++) {
					if (i == 4) {
						util.scrollByVisibleElement(driver, logger, nav.tabName(driver, TabNames[i]));
						util.pause(logger, "1");
						util.clickOn(logger, nav.tabName(driver, TabNames[i]));
						util.verifyElementByXpath(logger, nav.label(driver, FieldNames[i], TabNames[i]));
						util.scrollByVisibleElement(driver, logger, nav.label(driver, FieldNames[i], TabNames[i]));
						util.pause(logger, "1");
						String DestinationOfficeCityInTravelPlan = util.getElementValue(logger,
								nav.text(driver, FieldNames[i], TabNames[i]));
						if (arr1[i].equals(InitialGCPData[i])) {
							if (DestinationOfficeCityInTravelPlan.contains(InitialGCPData[i])) {
								logger.log(LogStatus.PASS,
										"Destination Office City In TravelPlan " + DestinationOfficeCityInTravelPlan
												+ " matches the Initial payload data " + InitialGCPData[i]);
							} else {
								logger.log(LogStatus.FAIL,
										"Destination Office City In TravelPlan " + DestinationOfficeCityInTravelPlan
												+ " not matches the Initial payload data " + InitialGCPData[i]);
							}

						} else {
							if (DestinationOfficeCityInTravelPlan.contains(arr1[i])) {
								logger.log(LogStatus.PASS,
										"Destination Office City In TravelPlan " + DestinationOfficeCityInTravelPlan
												+ " matches the Updated payload data " + arr1[i]);
							} else {
								logger.log(LogStatus.FAIL,
										"Destination Office City In TravelPlan " + DestinationOfficeCityInTravelPlan
												+ " not matches the Updated payload data " + arr1[i]);
							}
						}
					} else if (i != 3 && i != 4 && arr1[i].equals(InitialGCPData[i])) {
						if (TabNames[i].isEmpty() == false) {
							util.verifyElementByXpath(logger, nav.tabName(driver, TabNames[i]));
							util.scrollByVisibleElement(driver, logger, nav.tabName(driver, TabNames[i]));
							util.pause(logger, "1");
							util.clickOn(logger, nav.tabName(driver, TabNames[i]));
						}
						util.verifyElementByXpath(logger, nav.label(driver, FieldNames[i], TabNames[i]));
						util.scrollByVisibleElement(driver, logger, nav.label(driver, FieldNames[i], TabNames[i]));
						util.pause(logger, "1");
						if (i == 6) {
							if (isClientName = true) {
								util.verifyNullTextByValue(logger,
										nav.text(driver, "Unlisted Client Name", TabNames[i]));
								util.compareTwoStrings(logger,
										util.getElementValue(logger, portal.text(driver, FieldNames[i])),
										InitialGCPData[i]);
							} else {
								util.verifyNullTextByValue(logger, portal.text(driver, FieldNames[i]));
								util.compareTwoStrings(logger,
										util.getElementValue(logger,
												nav.text(driver, "Unlisted Client Name", TabNames[i])),
										InitialGCPData[i]);
							}

						} else {
							util.compareTwoStrings(logger,
									util.getElementValue(logger, portal.text(driver, FieldNames[i])),
									InitialGCPData[i]);
						}

					} else if (i == 3) {
						// Ignore
					} else { // if (i != 3 && arr1[i] != InitialGCPData[i]), i!=4
						if (TabNames[i].isEmpty() == false) {
							util.verifyElementByXpath(logger, nav.tabName(driver, TabNames[i]));
							util.scrollByVisibleElement(driver, logger, nav.tabName(driver, TabNames[i]));
							util.pause(logger, "1");
							util.clickOn(logger, nav.tabName(driver, TabNames[i]));
						}
						util.verifyElementByXpath(logger, nav.label(driver, FieldNames[i], TabNames[i]));
						util.scrollByVisibleElement(driver, logger, nav.label(driver, FieldNames[i], TabNames[i]));
						util.pause(logger, "1");
						if (i == 6) {
							if ((isClientName = true && getInputData(TestName, "isClientName").contains("true"))
									|| (isClientName = false
											&& getInputData(TestName, "isClientName").contains("true"))) {
								util.compareTwoStrings(logger,
										util.getElementValue(logger, portal.text(driver, FieldNames[i])), arr1[i]);
								util.verifyNullTextByValue(logger,
										nav.text(driver, "Unlisted Client Name", TabNames[i]));
							} else if ((isClientName = true && getInputData(TestName, "isClientName").contains("false"))
									|| (isClientName = false
											&& getInputData(TestName, "isClientName").contains("false"))) {
								util.verifyNullTextByValue(logger, portal.text(driver, FieldNames[i]));
								util.compareTwoStrings(logger, util.getElementValue(logger,
										nav.text(driver, "Unlisted Client Name", TabNames[i])), arr1[i]);
							}
							/*
							 * else if(isClientName = false && getInputData(TestName,
							 * "isClientName").contains("true")) { util.compareTwoStrings(logger,
							 * util.getElementValue(logger, nav.text(driver, FieldNames[i], TabNames[i])),
							 * arr1[i]); util.verifyNullTextByValue(logger, nav.text(driver,
							 * "Unlisted Client Name", TabNames[i])); }else if(isClientName = false &&
							 * getInputData(TestName, "isClientName").contains("false")) {
							 * util.verifyNullTextByValue(logger, nav.text(driver, FieldNames[i],
							 * TabNames[i])); util.compareTwoStrings(logger, util.getElementValue(logger,
							 * nav.text(driver,"Unlisted Client Name",TabNames[i])), arr1[i]); }
							 */
						} else {
							util.compareTwoStrings(logger,
									util.getElementValue(logger, portal.text(driver, FieldNames[i])), arr1[i]);
						}

					}
				}
				logger.log(LogStatus.PASS,
						"Test method: Passed ==> validate_Updated_Values_In_Travel_Plan__From_GCP_Restaffing_RestaffingModified_IntraClientMovement_HR_TASK");

			} else {
				logger.log(LogStatus.FAIL,
						"Failed to redirect to Travel plan form view from 'GCP Restaffing Restaffing Modified Intra Client Movement' HR Task");
			}
		} catch (

		Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test methhod: Failed to validate Updated fields from HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
			logger.log(LogStatus.FAIL,
					"Test method:  Failed to validate Updated fields from HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void Validate_GCP_HR_Task_Is_ClosedComplete(ExtentTest logger, String ShortDescription, String TemplateName,
			String AssigneeId, String description) {
		try {
			util.pause(logger, "5");
			util.endofpage(logger);
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			openRecord(logger, ShortDescription, "Short description", "HR Tasks", "Closed Complete");
			if (verifySelectedValueInDropdown(driver, "State", "").contains("Closed Complete")) {
				System.out.println("State field value contains Closed Complete");
				logger.log(LogStatus.PASS, "State field value contains Closed Complete");
			} else {
				System.out.println("State field value does not contain Closed Complete");
				logger.log(LogStatus.FAIL, "State field value does not contain Closed Complete");
			}
			String FieldForVerifyingDisabled[] = { "Number", "Template", "HR Case", "Travel Plan", "GCP Process Type",
					"Short description", "Description" };

			String FieldforVerifyingContainsByValue[] = { "Number", "Template", "HR Case", "Travel Plan",
					"GCP Process Type", "Short description", "Description" };
			String ValuesforVerifyingContainsByValue[] = { Auto_Generated_HR_Task_Number, TemplateName,
					Auto_Generated_HR_Case_Number, TravelPlanNumber, arr1[0], ShortDescription, description };
			for (int i = 0; i < 6; i++) {
				util.verifyTextContainsByValue(logger, nav.text(driver, FieldforVerifyingContainsByValue[i], ""),
						ValuesforVerifyingContainsByValue[i]);
			}
			for (String field : FieldForVerifyingDisabled) {
				util.verifyElementDisabled(logger, nav.text(driver, field, ""));
			}
			util.pause(logger, "2");
			util.verifyElementDisabled(logger, nav.dropdown(driver, "State", ""));
			// util.verifyElementDisabled(logger, nav.text(driver, "State", "")); // check 1
			// util.verifyElementReadonly(logger, nav.dropdown(driver, "State", "")); //
			// check 2
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Test method failed for HR Task:  " + ShortDescription);
			util.screenShotAndErrorMsg(logger, e, driver, "Test method failed for HR Task:  " + ShortDescription);
		}
		extent.endTest(logger);
		extent.flush();

	}

	/**
	 * @author k.p.balakrishnan user has to be either PMG ADMIN OR PMG FULFILLER
	 */
	@Test
	public void validate_HR_TASK_GCP_Restaffing_RestaffingModified_IntraClientMovement() {
		ExtentTest logger = extent.startTest(
				"Validate HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement",
				"Validate HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
		try {
			openGCPTravelPlanAndVerifyProcessType(logger);
			util.pause(logger, "5");
			util.endofpage(logger);
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			// util.scrollByVisibleElement(driver, logger, nav.tabName(driver, "Tasks"));
			System.out.println(EmployeeHostCountry);
			if (EmployeeHostCountry.contains("USA")) {
				Open_HR_TASK_Eligibility_Check_for_GCP();
				complete_HR_Task_Eligibility_Check_For_GCP_TravelPlan();
				util.pause(logger, "1");
				util.endofpage(logger);
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
				nav.tabName(driver, "Tasks").click();
				util.pause(logger, "2");
			}

			Open_HR_TASK_GCP_Restaffing_RestaffingModified_IntraClientMovement();
			ProcessType = arr1[0];

			validateGCPHRTaskFieldMappingAndEditability(logger,
					"PMG GCP Restaffing, Modified Restaffing or Intra Client Movement",
					"PMG GCP Restaffing, Modified Restaffing or Intra Client Movement",
					"T39883.02.admin");
			// Validate Button Functionality in the HR Task
			util.verifyElementByXpath(logger, nav.button(driver, "Update", ""));
			util.verifyElementByXpath(logger, nav.button(driver, "Create New TP and Close Complete", ""));
			util.verifyElementByXpath(logger, nav.button(driver, "Overwrite This TP and Close Complete", ""));
			util.verifyElementNotDisplayed(logger, nav.button(driver, "Close Complete", ""));
			Complete_HR_TASK_GCP_Restaffing_RestaffingModified_IntraClientMovement();
			validate_Updated_Values_In_Travel_Plan__From_GCP_Restaffing_RestaffingModified_IntraClientMovement_HR_TASK();
			// Add Sumanth method here
			Editabilityoffieldsforrestaffing();

			// openGCPTravelPlanAndVerifyProcessType(logger);
			OpenTravelPlan();
			Validate_GCP_HR_Task_Is_ClosedComplete(logger,
					"PMG GCP Restaffing, Modified Restaffing or Intra Client Movement",
					"PMG GCP Restaffing, Modified Restaffing or Intra Client Movement",
					"T39883.02.admin", "");

			logger.log(LogStatus.PASS,
					"Test method: Passed ==> Validate HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test methhod: Failed ==> Validate HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
			logger.log(LogStatus.FAIL,
					"Test method: Failed ==> Validate HR TASK : GCP Restaffing, Restaffing Modified, Intra Client Movement");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// GCP - UPDATES - SECOND MAJOR RELEASE
	// User Story 764313: Refined - PMG - CMS - GCP - Admin Table - PMG Cities and
	// States - Creation of new field for GCP City mapping
	/**
	 * @author k.p.balakrishnan
	 * User Story 764313
	 */
	@Test
	public void ValidateGCPCityFieldAndFieldMapping() {
		ExtentTest logger = extent.startTest("Creation Of New Field For GCP City Mapping",
				"Creation Of New Field For GCP City Mapping");
		try {
			String columnName = "GCP City";
			// 1. Verify 'GCP City' column in default list view
			verifyColumns(logger, columnName);
			verifyDefaultListView(logger, columnName);

			// Two flows
			// FLOW I. Create and validate New Record in form view
			// 4. Validate non mandatory text field
			// 5. Comma separated values will be allowed.
			ValidateNewPMGCitiesAndStatesRecordInFormView(logger);
			CreateNewPMGCitiesAndStatesRecord();

			// 2. Validate 'GCP City' field editability in list view
			// openRecord(logger, PMGName, "Name");
			util.mouseHover(logger, driver,  nav.tooltip(driver, "Show / hide filter", "", ""));
			util.clickOn(logger, nav.tooltip(driver, "Show / hide filter", "", ""));
			util.pause(logger, "3");
			setFilterConditions(logger, "Name", "starts with", PMGName, 1);
			util.pause(logger, "10");
			util.clickOn(logger, nav.tooltip(driver, "Run filter", "", ""));
			util.scrollByVisibleElement(driver, logger, nav.link(driver, "GCP City", ""));
			util.pause(logger, "5");
			VerifyFieldEditabilityInListView(logger, columnName);

			// 3. Validate editability in form view
			// 5. Comma separated values will be allowed.
			validateGCPCityEditabilityInPMGCitiesAndStatesFormView(logger);
			util.compareTwoStrings(logger, util.getElementValue(logger, nav.text(driver, "GCP City", "")), GCPCity);

			// End of flows
			// Verify One-to-Many mapping will be allowed
			logger.log(LogStatus.PASS, "Validation of GCP City Field And Field Mapping is successfull.");
			
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test method: Failed ==> Creation Of New Field For GCP City Mapping");
			logger.log(LogStatus.FAIL, "Test method: Failed ==> Creation Of New Field For GCP City Mapping");
		}

	}
	
	/**
	 * @author k.p.balakrishnan
	 * User Story 764313
	 */
	@Test
	public void ValidateGCPCityFieldAndFieldMappingForHistoricRecord() {
		ExtentTest logger = extent.startTest("Creation Of New Field For GCP City Mapping For a Historic Record",
				"Creation Of New Field For GCP City Mapping For a Historic Record");
		try {
			String columnName = "GCP City";
			// 1. Verify 'GCP City' column in default list view
			verifyColumns(logger, columnName);
			verifyDefaultListView(logger, columnName);

			// FLOW II. Validate Historic record
			util.clickOn(logger, nav.tooltip(driver, "Show / hide filter", "", ""));
			util.pause(logger, "3");
			setFilterConditions(logger,  "Name", "starts with", HistoricPMGName, 1);
			util.pause(logger, "10");
			util.clickOn(logger, nav.tooltip(driver, "Run filter", "", ""));
			// 2. Validate 'GCP City' field editability in list view
			VerifyFieldEditabilityInListView(logger, columnName);
			util.scrollByVisibleElement(driver, logger, nav.tooltip(driver, "Preview", "", ""));
			
			// 3. Validate editability in form view
			// 5. Comma separated values will be allowed.
			validateGCPCityEditabilityInPMGCitiesAndStatesFormView(logger);
			util.compareTwoStrings(logger, util.getElementValue(logger, nav.text(driver, "GCP City", "")), HistoricGCPCity);
			
			// 4. Validate non mandatory text field
			verifyNonMandatoryField(logger, columnName);
			logger.log(LogStatus.PASS, "Validation of GCP City Field And Field Mapping is successfull for Historic record.");
			
			// end of flows
			// Verify One-to-Many mapping will be allowed
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver,
					"Test method: Failed ==> Creation Of New Field For GCP City Mapping");
			logger.log(LogStatus.FAIL, "Test method: Failed ==> Creation Of New Field For GCP City Mapping");
		}

	}

	/**
	 * @author k.p.balakrishnan
	 * User Story 764313
	 */
	@Test
	public void CreateNewPMGCitiesAndStatesRecord() {
		ExtentTest logger = extent.startTest("Create New PMG Cities And States Record",
				"Create New PMG Cities And States Record");
		try {
			String currentTitle = driver.getTitle();
			if(currentTitle.contains("New Record | PMG Cities and States | ServiceNow")) {
				logger.log(LogStatus.INFO, "PMG Admin already logged in and current in PMG Cities And States Record");
			}else if(currentTitle.contains("PMG Cities and States | ServiceNow")) {
				logger.log(LogStatus.INFO, "PMG Admin already logged in and current in PMG Cities And States Table");
				util.clickOn(logger, nav.button(driver, "New", ""));
				util.waitForPageToLoadCompletely(logger, driver);
			}else {
				logger.log(LogStatus.INFO, "PMG Admin/user in different web page and so redirecting to current page.");
				openPMGCitiesAndStatesTable();
				util.clickOn(logger, nav.button(driver, "New", ""));
				util.waitForPageToLoadCompletely(logger, driver);
			}
			/*
			String getCurrentURL = driver.getCurrentUrl();
			if (getCurrentURL.contains("u_pmg_cities_and_states")) {
				logger.log(LogStatus.INFO, "PMG Admin already logged in and current in PMG Cities And States Record");
			} else {
				logger.log(LogStatus.INFO, "PMG Admin/user in different web page and so redirecting to current page.");
				openPMGCitiesAndStatesTable();
				util.clickOn(logger, nav.button(driver, "New", ""));
				util.waitForPageToLoadCompletely(logger, driver);
			}
			if (nav.tooltip(driver, "PMG Cities and States Context Menu", "", "") != null) {
				logger.log(LogStatus.PASS, "Navigated successfully to PMG Cities and States table!");
			}
			*/
			String[] FieldsInPMGCitiesAndStatesRecordFormView = { "City", "Name", "Country","State",
					"State Abbreviation", "GCP City" };
			String[] FieldType = { "textbox", "textbox", "textbox", "textbox", "textbox","textbox" };
			String[] FieldValue = { PMGCity, PMGName, PMGCountry, PMGState, PMGStateAbbreviation, GCPCity };
			for (int i = 0; i < FieldsInPMGCitiesAndStatesRecordFormView.length; i++) {
				populateFieldsbyType(logger, FieldsInPMGCitiesAndStatesRecordFormView[i], FieldType[i], FieldValue[i]);
			}
			if (PMGActive.contains("true")) {
				util.clickOn(logger, nav.checkbox(driver, "Active", ""));
			}
			
			if(PMGCountry.contains("USA")) {
				populateFieldsbyType(logger, "Market_Unit (US)", "dropdown", Market_Unit_US);
			}

			util.clickOn(logger, nav.button(driver, "Submit", ""));
			util.waitForPageToLoadCompletely(logger, driver);
			util.pause(logger, "3");
			
			
			/*
			 * for(String FieldInPMGCitiesAndStatesRecordFormView:
			 * FieldsInPMGCitiesAndStatesRecordFormView) { populateFieldsbyType(logger,
			 * FieldInPMGCitiesAndStatesRecordFormView, "", getCurrentURL); }
			 */

			if (nav.tooltip(driver, "PMG Cities and States Context Menu", "", "") != null) {
				logger.log(LogStatus.PASS, "PMG Cities and States record is created and navigated to List view");
			} else {
				logger.log(LogStatus.FAIL, "PMG Cities and States record is not created.");
			}
		} catch (Exception e) {
			logger.log(LogStatus.INFO, "Unable to Validate New PMG Cities And States Record");
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to Validate New PMG Cities And States Record");
		}
	}
	
	/**
	 * @author k.p.balakrishnan
	 * User Story 764313
	 */
	public void ValidateNewPMGCitiesAndStatesRecordInFormView(ExtentTest logger) {
		logger = extent.startTest("Validate New PMG Cities And States Record in form view",
				"Validate New PMG Cities And States Record in form view");
		try {
			util.clickOn(logger, nav.button(driver, "New", ""));
			util.waitForPageToLoadCompletely(logger, driver);
			String[] LabelsInPMGCitiesAndStatesRecordFormView = { "City", "Country", "Name", "State",
					"State Abbreviation", "Active", "GCP City" };
			// Validate labels present in Create New PMG Cities And States Record
			for (String LabelInPMGCitiesAndStatesRecordFormView : LabelsInPMGCitiesAndStatesRecordFormView) {
				if (util.verifyElementByXpath(logger,
						nav.label(driver, LabelInPMGCitiesAndStatesRecordFormView, "")) == true) {
					logger.log(LogStatus.PASS, LabelInPMGCitiesAndStatesRecordFormView
							+ " is present in the form view of PMG Cities And States Record");
					screenShotAndInfoMsg(logger, driver, LabelInPMGCitiesAndStatesRecordFormView
							+ " is present in the form view of PMG Cities And States Record");
				} else {
					logger.log(LogStatus.FAIL, LabelInPMGCitiesAndStatesRecordFormView
							+ " is absent in the form view of PMG Cities And States Record");
				}
			}

			// Validate non mandatory fields in Create New PMG Cities And States Record
			for (String LabelInPMGCitiesAndStatesRecordFormView : LabelsInPMGCitiesAndStatesRecordFormView) {
				verifyNonMandatoryField(logger, LabelInPMGCitiesAndStatesRecordFormView);
			}
			util.isEnabled(logger, nav.text(driver, "GCP City", ""));
			logger.log(LogStatus.PASS, "Validated New PMG Cities And States Record in form view");
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to Validate New PMG Cities And States Record in form view");
			util.screenShotAndErrorMsg(logger, e, driver,
					"Unable to Validate New PMG Cities And States Record  in form view");
		}
	}
	
	/**
	 * @author k.p.balakrishnan
	 * User Story 764313
	 */
	public void validateGCPCityEditabilityInPMGCitiesAndStatesFormView(ExtentTest logger) {
		logger = extent.startTest("Validate 'GCP City' editability in PMG Cities And States record Form View",
				"Validate 'GCP City' editability in PMG Cities And States record Form View");
		try {
			util.clickOn(logger, nav.tooltip(driver, "Preview", "", ""));
			util.clickOn(logger, nav.link(driver, "Open Record", ""));
			util.waitForPageToLoadCompletely(logger, driver);
			logger.log(LogStatus.PASS, "Record is opened");
			util.isEnabled(logger, nav.text(driver, "GCP City", ""));
			
		} catch (Exception e) {
			logger.log(LogStatus.FAIL,
					"Unable to validate 'GCP City' editability in PMG Cities And States record Form View");
			util.screenShotAndErrorMsg(logger, e, driver,
					"Unable to validate 'GCP City' editability in PMG Cities And States record Form View");
		}
	}
	public String MultiUpdatesGCPCityValue; 
	public String[] GCPCities;
	/**
	 * @author k.p.balakrishnan
	 * User Story 764313
	 */
	@Test
	public void validateOnePMGCityMappedToManyGCPCityByMultipleRecords() {
		ExtentTest logger = extent.startTest("Validate One PMG City Mapped To Many GCP City","Validate One PMG City Mapped To Many GCP City");
		try {
			if(GCPCity != null) {
				MultiUpdatesGCPCityValue=GCPCity;
				GCPCities= MultiUpdatesGCPCityValue.split(",");
				String NumberOfMultiGCPCityUpdatesForAsinglePMGCity = getInputData(TestName, "NumberOfMultiGCPCityUpdatesForAsinglePMGCity");
				int n= Integer.parseInt(NumberOfMultiGCPCityUpdatesForAsinglePMGCity);
				for(int i=0; i<GCPCities.length; i++) {
					GCPCity = GCPCities[i];
					CreateNewPMGCitiesAndStatesRecord();
				}
				
			}else if(HistoricGCPCity !=null) {
				MultiUpdatesGCPCityValue=HistoricGCPCity; //Stores all city names 
			}
			GCPCities = MultiUpdatesGCPCityValue.split(",");
			
			
			//String MultiUpdatesGCPCityValue = getInputData(TestName, "MultiUpdatesGCPCityValue");
			
			//String[] GCPCities = MultiUpdatesGCPCityValue.split("|");
			//ArrayList<String> ListOfGCPCityValuesUsedToCreatePMGStatesAndCities = (ArrayList<String>) Arrays.asList(GCPCities);
			
			//AT list view
			util.mouseHover(logger, driver,  nav.tooltip(driver, "Show / hide filter", "", ""));
			util.clickOn(logger, nav.tooltip(driver, "Show / hide filter", "", ""));
			util.pause(logger, "3");
			if(GCPCity !=null) {
				setFilterConditions(logger, "Name", "is", PMGName, 1);
			}else if(HistoricGCPCity !=null){
				setFilterConditions(logger, "Name", "is", HistoricPMGName, 1);
			}
			util.clickOn(logger, nav.tooltip(driver, "Run filter", "", ""));
			util.scrollByVisibleElement(driver, logger, nav.link(driver, "GCP City", ""));
			util.pause(logger, "5");
			
			ArrayList<String> ListOfGCPCityValuesInTable = nav.getColumnValuesInTableBasedOnTableId(logger, driver, "u_pmg_cities_and_states_table","GCP City", "");
			String[] ListOfGCPCityValuesInTableForValidation = new String[ListOfGCPCityValuesInTable.size()];
			int count=0;
			for(int i=0; i<ListOfGCPCityValuesInTable.size();i++) {
				ListOfGCPCityValuesInTableForValidation[i]=ListOfGCPCityValuesInTable.get(i);
				for(int j=0; j<GCPCities.length; j++) {
					if(ListOfGCPCityValuesInTableForValidation[i].equals(GCPCities[j])) {
						count++;
						logger.log(LogStatus.PASS, "One PMG City Mapped To Many GCP City");
					}
				}
				
			}
			if(count==GCPCities.length) {
				logger.log(LogStatus.PASS, "One PMG City Mapped To Many GCP City");
			}else {
				logger.log(LogStatus.FAIL, "One PMG City is not mapped To Many GCP City");
			}
		}catch (Exception e) {
			logger.log(LogStatus.FAIL,
					"Unable to validate One PMG City Mapped To Many GCP City");
			util.screenShotAndErrorMsg(logger, e, driver,
					"Unable to validate One PMG City Mapped To Many GCP City");
		}
	}
	
	/**
	 * @author k.p.balakrishnan
	 * User Story 764313
	 */
	@Test
	public void validateOnePMGCityMappedToManyGCPCityInASingleRecord() {
		ExtentTest logger = extent.startTest("Validate One PMG City Mapped To Many GCP City in a single record","Validate One PMG City Mapped To Many GCP City in a single record");
		try {
			if(GCPCity !=null) {
				CreateNewPMGCitiesAndStatesRecord();
				MultiUpdatesGCPCityValue=GCPCity;
			}else if(HistoricGCPCity !=null) {
				MultiUpdatesGCPCityValue=HistoricGCPCity; //Stores all city names 
			}
			//GCPCities = MultiUpdatesGCPCityValue.split(",");
			//ArrayList<String> ListOfGCPCityValuesUsedToCreatePMGStatesAndCities = (ArrayList<String>) Arrays.asList(GCPCities);
			
			//AT list view
			util.mouseHover(logger, driver,  nav.tooltip(driver, "Show / hide filter", "", ""));
			util.clickOn(logger, nav.tooltip(driver, "Show / hide filter", "", ""));
			util.pause(logger, "3");
			if(GCPCity !=null) {
				setFilterConditions(logger, "Name", "is", PMGName, 1);
			}else if(HistoricGCPCity !=null){
				setFilterConditions(logger, "Name", "is", HistoricPMGName, 1);
			}
			util.clickOn(logger, nav.tooltip(driver, "Run filter", "", ""));
			util.scrollByVisibleElement(driver, logger, nav.link(driver, "GCP City", ""));
			util.pause(logger, "5");
			
			ArrayList<String> ListOfGCPCityValuesInTable = nav.getColumnValuesInTableBasedOnTableId(logger, driver,"u_pmg_cities_and_states_table", "GCP City", "");
			String[] ListOfGCPCityValuesInTableForValidation = new String[ListOfGCPCityValuesInTable.size()];
			for(int i=0; i<ListOfGCPCityValuesInTable.size();i++) {
				ListOfGCPCityValuesInTableForValidation[i]=ListOfGCPCityValuesInTable.get(i);
				if(ListOfGCPCityValuesInTableForValidation[i].equalsIgnoreCase(MultiUpdatesGCPCityValue)) {
					logger.log(LogStatus.PASS, "One PMG City Mapped To Many GCP City");
				}else {
					logger.log(LogStatus.FAIL, "One PMG City is not mapped To Many GCP City");
				}
			}
			
		}catch (Exception e) {
			logger.log(LogStatus.FAIL,
					"Unable to validate One PMG City Mapped To Many GCP City in a single record");
			util.screenShotAndErrorMsg(logger, e, driver,
					"Unable to validate One PMG City Mapped To Many GCP City in a single record");
		}
	}
	
	/**
	 * @author k.p.balakrishnan
	 * User Story 764313
	 */
	@Test
	public void DeletePMGCityAndStatesRecord() {
		ExtentTest logger = extent.startTest("Delete PMG City And States Record",
				"Delete PMG City And States Record");
		try {
			openPMGCitiesAndStatesTable();
			if(GCPCity!= null) {
				util.clickOn(logger, nav.tooltip(driver, "Show / hide filter", "", ""));
				util.pause(logger, "3");
				setFilterConditions(logger, "Name", "is", PMGName, 1);
				util.pause(logger, "10");
				util.clickOn(logger, nav.tooltip(driver, "Run filter", "", ""));
				
				if (driver.findElements(By.xpath("//label[@class='checkbox-label']")).size() > 0) {
					util.clickOn(logger, driver.findElement(By.xpath("//label[@class='checkbox-label']")));
					Select dropDown = new Select(
							driver.findElement(By.xpath("//select[contains(@class,'list_action_option')]")));
					screenShotAndInfoMsg(logger, driver, "Filtered Record");
					// changed
					util.clickOn(logger, dropDown.getFirstSelectedOption());
					util.clickOn(logger, portal.label(driver, "Delete"));
					
					util.pause(logger, "5");
					// clicking on delete button in pop-up
					util.clickOn(logger, driver.findElement(By.xpath("//*[@id='ok_button']")));
					driver.navigate().refresh();
					util.waitForPageToLoadCompletely(logger, driver);
				}
			}else if(HistoricGCPCity!=null) {
					//No need to delete
				}
		} catch (Exception e) {

			util.screenShotAndErrorMsg(logger, e, driver, "unable to Delete PMG City And States Record");
		}
		extent.endTest(logger);
		extent.flush();
	}
	
	/**
	 * @author k.p.balakrishnan
	 * User Story 764313
	 */
	@Test
	public void validateCityFieldMapping() {
		ExtentTest logger = extent.startTest("Validate City Field Mapping",
				"Validate City Field Mapping");
		try {
			String[] ListOfCities = MultiUpdatesGCPCityValue.split(",");
			for(int i=0; i<=ListOfCities.length; i++) {
				getDataFabricAccessTokenForGCP();
				if(i==ListOfCities.length) {
					EmployeeHostCity = getInputData(TestName, "EmployeeHostCity");
				}else {
					EmployeeHostCity= ListOfCities[i];
				}
				PostGCPCall();
				getTravelPlanNumberFromCreatedGCPTravelPlan();
				openCreatedGCP_TravelPlanInFormView();
				util.pause(logger, "1");
				util.verifyElementByXpath(logger, nav.tabName(driver, "Main Details"));
				util.scrollByVisibleElement(driver, logger, nav.tabName(driver, "Main Details"));
				util.pause(logger, "3");
				util.clickOn(logger,  nav.tabName(driver, "Main Details"));
				util.pause(logger, "3");
				util.verifyElementByXpath(logger, nav.label(driver, "Destination Office City", "Main Details"));
				util.scrollByVisibleElement(driver, logger, nav.label(driver, "Destination Office City", "Main Details"));
				util.pause(logger, "4");
				if(GCPCity !=null) {
					if(PMGName.equalsIgnoreCase(util.getElementValue(logger,  nav.text(driver, "Destination Office City", "Main Details")))) {
						logger.log(LogStatus.PASS, "Field mapping of Destination Office City is successful");
						screenShotAndInfoMsg(logger, driver, "Field mapping of Destination Office City is successful");
					}else {
						logger.log(LogStatus.FAIL, "Field mapping of Destination Office City is not successful");
					}
				}else if(HistoricGCPCity !=null) {
					if(HistoricPMGName.equalsIgnoreCase(util.getElementValue(logger,  nav.text(driver, "Destination Office City", "Main Details")))) {
						logger.log(LogStatus.PASS, "Field mapping of Destination Office City is successful");
						screenShotAndInfoMsg(logger, driver, "Field mapping of Destination Office City is successful");
					}else {
						logger.log(LogStatus.FAIL, "Field mapping of Destination Office City is not successful");
					}
				}
			}
		}catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to Validate City Field Mapping");
			util.screenShotAndErrorMsg(logger, e, driver,
					"Unable to Validate City Field Mapping");
		}
		extent.endTest(logger);
		extent.flush();
	}
	
	@Parameters({ "Action", "ProjectVisaDataType","HRTaskName" })
	@Test
	public void CloseSpecificHRTask(String Status, String ProjectVisaDataType,String HRTaskName) throws AWTException {
		ExtentTest logger = extent.startTest("Close HR Task");
		try {
			OpenTravelPlan();
			util.pause(logger, "3");
			util.scrollToElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			scrollToElementToCenter(nav.label(driver, "HRC", "HR Cases"),driver);
			//util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");

			util.clickOn(logger, driver.findElement(By.xpath("(//*[text()='HR Tasks']/following::table/tbody//tr/td[text()='"+HRTaskName+"']/parent::tr/td[3]/a)")));
			util.pause(logger, "11");
			if(nav.checkbox(driver, "Document Validated", "").isEnabled())
			{
			util.clickOn(logger, portal.backgroundText(driver, "Document Validated"));
			}
			switch (Status) {
			case "CancelTravelRequest":
				util.scrollByVisibleElement(driver, logger, portal.textArea(driver, "Confirmation Comments"));
				util.setTextValue(logger, driver, portal.textArea(driver, "Confirmation Comments"), "Cancelled");
				util.clickOn(logger, nav.button(driver, "Cancel Travel Request", ""));
				util.pause(logger, "7");
				util.clickOn(logger, portal.button(driver, "Back"));
				break;
			case "ConfirmTravelRequest":
				util.verifyElementByXpath(logger, nav.label(driver, "Project Visa Type", ""));
				if (ProjectVisaDataType.contains("dropdown")) {
					util.selectBoxByValue(logger, portal.dropdown(driver, "Project Visa Type"), ProjectVisaType);
				} else if (ProjectVisaDataType.contains("droplist")) {
					util.setTextWithEnter(logger, nav.text(driver, "Project Visa Type", ""), ProjectVisaType);
				}
				util.selectBoxByValue(logger, portal.dropdown(driver, "Program Name/Transfer Type"),
						getInputData(TestName, "ProgramName_TransferType"));
				VerifyPopulateAssignedTo(logger, "T39883.01.fulfiller");
				util.clickOn(logger, nav.button(driver, "Confirm Travel Request", ""));
				util.pause(logger, "10");
				logger.log(LogStatus.PASS, "HR Task is closed");
			}

		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to change status of travel plan");
		}
		extent.endTest(logger);
		extent.flush();
	}

	public void CompleteTravelerDataCollectionRPGCP() {
		ExtentTest logger = extent.startTest("Traveler Data Collection", "User completes Traveler Data Collection RP");
		travelduration = getInputData(TestName, "Travel Duration");
		percentworkday = getInputData(TestName, "Percent Workday");
		try {
			System.out.println("working");
			util.pause(logger, "5");
			searchAndOpenRP(logger, "Traveler Data Collection");
			driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(5));
			// populate fields
			populateFieldsbyType(logger, "Marital Status", "droplist", getInputData(TestName, "Marital Status"));
			populateFieldsbyType(logger, "Do you hold another citizenship?", "droplist", "No");
			populateFieldsbyType(logger, "Do you plan for any family members (dependents) to accompany you?",
					"droplist", getInputData(TestName, "Will you be traveling with dependents?"));
			util.pause(logger, "3");
			populateFieldsbyType(logger, "Are you currently in the Host Country?", "dropdown", "No");
			populateFieldsbyType(logger, "Specify the Processing Type", "dropdown", "L1 Blanket");
			populateFieldsbyType(logger, "Please provide the name of your Accenture leadership in the destination country.", "textbox", "TEST AUTOMATION");
			populateFieldsbyType(logger, "Please provide the ", "textbox", "test automation");
			populateFieldsbyType(logger, "Immigration Compliance Agreement -Employee", "dropdown", "No");
			populateFieldsbyType(logger, "Have you taken any unpaid leave in the last 12 months?", "dropdown", "No");
			populateFieldsbyType(logger, "Provide your current home address, including postcode/zip code and county/province.", "textbox", "TEST AUTOMATION");
			populateFieldsbyType(logger, "Data Protection Confirmation (UK):", "dropdown", "No");	
			
			// submit
			util.scrollByVisibleElement(driver, logger, portal.button(driver, "Submit"));
			//util.clickOn(logger, portal.button(driver, "Submit"));
			util.clickOn(logger, driver.findElement(By.xpath("//button[contains(text(),'Submit')]")));
			util.pause(logger, "5");
			logger.log(LogStatus.PASS, "Traveler Data Collection RP is closed");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to complete Traveler Data Collection");
		}
		extent.endTest(logger);
	}

	@Test
	public void GCPVisaTypeFieldVerificationInPMGVisaTypesTable() {
		ExtentTest logger = extent.startTest("GCP Visa Types field Verification",
				"GCP Visa Type Field Verification In PMG Visa Types Table");
		try {
			openPMGVisaTypesTable(logger);
			nav.verifyTableElements(logger, "GCP Visa Type", "others", "");
			util.clickOn(logger, portal.button(driver, "New"));
			screenShotAndInfoMsg(logger, driver, "New Record creation");
			util.waitTillElementIsVisible(logger, driver, nav.label(driver, "Country", ""));
			util.setText(logger, nav.text(driver, "Country", ""), getInputData(TestName, "Country/Location"));
			util.selectBoxByValue(logger, nav.dropdown(driver, "Visa Type", ""),
					getInputData(TestName, "validVisaType"));
			util.clickOn(logger, portal.button(driver, "Submit"));
			util.clickOn(logger, nav.tooltip(driver, "Show / hide filter", "", ""));
			util.pause(logger, "3");
			setFilterConditions(logger, "Country", "is", getInputData(TestName, "Country/Location"), 1);
			util.clickOn(logger, nav.tooltip(driver, "Run filter", "", ""));
			screenShotAndInfoMsg(logger, driver, "Record filtered");
			util.pause(logger, "3");
			util.setText(logger, driver.findElement(By.xpath("//input[@aria-label='Search column: visa type']")),
					getInputData(TestName, "validVisaType"));
			driver.findElement(By.xpath("//input[@aria-label='Search column: visa type']")).sendKeys(Keys.ENTER);
			util.pause(logger, "10");
			if (nav.getTableCellText(logger, driver, "GCP Visa Type", "").equalsIgnoreCase("")) {
				logger.log(LogStatus.INFO,
						"GCP Visa Type is non mandatory field and new record got created without value in it.");
			}
			verifyDefaultListView(logger, "GCP Visa Type");
			editTableText(logger, "GCP Visa Type", "H1B,h1b,H1b");
			if (nav.getTableCellText(logger, driver, "GCP Visa Type", "").equalsIgnoreCase("H1B,h1b,H1b")) {
				logger.log(LogStatus.INFO, "GCP Visa Type separated by comma is allowed");
			}

			if (driver.findElements(By.xpath("//label[@class='checkbox-label']")).size() > 0) {
				util.clickOn(logger, driver.findElement(By.xpath("//label[@class='checkbox-label']")));
				Select dropDown = new Select(
						driver.findElement(By.xpath("//select[contains(@class,'list_action_option')]")));
				util.clickOn(logger, dropDown.getFirstSelectedOption());
				util.clickOn(logger, portal.label(driver, "Delete"));
				util.pause(logger, "5");
				// clicking on delete button in pop-up
				util.clickOn(logger, driver.findElement(By.xpath("//*[@id=\"ok_button\"]")));
				driver.navigate().refresh();
				util.waitForPageToLoadCompletely(logger, driver);
				if (driver.findElements(By.xpath("//label[@class='checkbox-label']")).size() == 0) {
					screenShotAndInfoMsg(logger, driver, "visa record is deleted");
				}
			}
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "GCP Visa Type Field Verification In PMG Visa Types Table Failed");
			util.screenShotAndErrorMsg(logger, e, driver,
					"GCP Visa Type Field Verification In PMG Visa Types Table Failed");
		}
		extent.endTest(logger);
		extent.flush();
	}

	// Created by: hermaine.c.t.canania
	// Verification of GCP Visa Type field
	@Test
	public void VerificationOfGCPVisaTypeFieldInPMGVisaTypesTable() {
		ExtentTest logger = extent.startTest("GCP Visa Types field Verification",
				"GCP Visa Type Field Verification In PMG Visa Types Table");
		try {

			String CountryName = getInputData(TestName, "Country/Location");
			String GCPVisaTypeValue = getInputData(TestName, "validVisaType");
			openPMGVisaTypesTable(logger);
			nav.verifyTableElements(logger, "GCP Visa Type", "others", "");
			openRecord(logger, CountryName, "Country");
			util.pause(logger, "10");
			util.verifyElementByXpath(logger, nav.label(driver, "GCP Visa Type", ""));
			util.setText(logger, nav.text(driver, "GCP Visa Type", ""), GCPVisaTypeValue);
			util.pause(logger, "2");
			util.clickOn(logger, nav.button(driver, "Update", ""));

			//Relogin as admin
			loginAsAdmin();
			openPMGVisaTypesTable(logger);
			openRecord(logger, GCPVisaTypeValue, "GCP Visa Type");
			util.pause(logger, "10");

			
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "GCP Visa Type Field Verification In PMG Visa Types Table Failed");
			util.screenShotAndErrorMsg(logger, e, driver,
					"GCP Visa Type Field Verification In PMG Visa Types Table Failed");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void verifyPMGVisaTypesTableIsNotVisibleToFulfiller() {
		ExtentTest logger = extent.startTest("verify PMG Visa Types Table Is Not Visible To Fulfiller",
				"verify PMG Visa Types Table Is Not Visible To Fulfiller");
		try {
			browserHelper.navigateTo(logger, getInputData("navigate", "NAVPAGEURL"));
			List<String> item = new ArrayList<String>();
			item.add("People Mobility");
			item.add("Admin - Tables");
			verifyTableIsNotVisible(logger, item.get(0), item, "PMG Visa Types", "T39377.05");
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "verification of PMG Visa Types Table failed");
			util.screenShotAndErrorMsg(logger, e, driver, "verification of PMG Visa Types Table failed");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void ErrorHandlingByAdmin() {
		ExtentTest logger = extent.startTest("Error Handling By Admin", "Error Handling By Admin");
		try {
			getTravelPlanNumberFromCreatedGCPTravelPlan();
			openCreatedGCP_TravelPlanInFormView();
			util.clickOn(logger, nav.label(driver, "Main Details", ""));
			Select s = new Select(nav.dropdown(driver, "Project Visa Type", ""));
			String visaTypeValue = s.getFirstSelectedOption().getText();
			logger.log(LogStatus.INFO, "Project visa type value is "+visaTypeValue);
			scrollToElementToCenter(nav.label(driver, "Destination Office City", ""), driver);
			String DestinationOfficeCityValue = nav.text(driver, "Destination Office City", "").getText();
			logger.log(LogStatus.INFO, "Destination Office City is "+DestinationOfficeCityValue);
			
			if (s.getFirstSelectedOption().getText().equalsIgnoreCase("-- None --")) {
				logger.log(LogStatus.PASS, "Project Visa Type field is empty");
				screenShotAndInfoMsg(logger, driver, "Project Visa Type field is empty");
			}
			scrollToElementToCenter(nav.label(driver, "Destination Office City", ""), driver);
			if (nav.text(driver, "Destination Office City", "").getText().equals("")) {
				logger.log(LogStatus.PASS, "Destination Office City field is empty");
				screenShotAndInfoMsg(logger, driver, "Destination Office City field is empty");
			}
			DataMismatchUpdate();
			openPMGVisaTypesTable(logger);
			util.clickOn(logger, portal.button(driver, "New"));
			util.waitTillElementIsVisible(logger, driver, nav.label(driver, "Country", ""));
			util.setText(logger, nav.text(driver, "Country", ""), getInputData(TestName, "Country/Location"));
			util.selectBoxByValue(logger, nav.dropdown(driver, "Visa Type", ""),
					getInputData(TestName, "ProjectVisaType"));
			util.setText(logger, nav.text(driver, "GCP Visa Type", ""), getInputData(TestName, "ProposedVisaType"));
			screenShotAndInfoMsg(logger, driver, "New Visa Record");
			util.clickOn(logger, portal.button(driver, "Submit"));
			openPMGCitiesAndStatesTable();
			CreateNewPMGCitiesAndStatesRecord();
			getDataFabricAccessTokenForGCP();
			PostGCPCallUsingExistingDocId("Payload1");
			util.pause(logger, "10");
			OpenTravelPlan();
			util.clickOn(logger, nav.label(driver, "Main Details", ""));
			scrollToElementToCenter(nav.label(driver, "Destination Office City", ""), driver);
			if (nav.text(driver, "Destination Office City", "").getAttribute("value").equals(PMGCity)) {
				logger.log(LogStatus.PASS, "Destination Office City field is auto populated correctly after error handling of data mismatch");
			}
			closeCompleteEligibilityCheckForGCPHRTask("NoReuseOfExistingH1BNominationTravelPlan");
			TravelerOpenCreatedGCP_TravelPlanIn_PMG_Dashboard_Via_SysID();
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Your actions"));
			util.pause(logger, "5");
			util.clickOn(logger, portal.link(driver, "See tasks"));
			util.pause(logger, "5");
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Traveler Data Collection"));
			util.clickOn(logger, driver.findElement(By.xpath("//*[text()='Traveler Data Collection']/following::button[1]")));
            util.pause(logger, "7");
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Destination/Receiving City"));
            if(driver.findElement(By.xpath("//div[contains(@id,'city')]/a/span")).getText().equalsIgnoreCase(PMGCity))
            {
            	logger.log(LogStatus.PASS, "Destination/Receiving City is autp populated correctly in Traveler Data Collection RP");
            }
            logger.log(LogStatus.INFO, "Verification of Visa and city auto population in newly created TP, after mapping is done correctly");
            getDataFabricAccessTokenForGCP();
    		PostGCPCall("Payload2");
    		loginAsAdmin();
    		OpenTravelPlan();
    		util.clickOn(logger, nav.label(driver, "Main Details", ""));
			util.scrollByVisibleElement(driver, logger, nav.dropdown(driver, "Project Visa Type", ""));
			Select s1 = new Select(nav.dropdown(driver, "Project Visa Type", ""));
			String visaTypeValue1 = s1.getFirstSelectedOption().getText();
			logger.log(LogStatus.INFO, "Project visa type value is "+visaTypeValue1);
			if(visaTypeValue1.equalsIgnoreCase(getInputData(TestName, "ProjectVisaType")))
			{
				logger.log(LogStatus.PASS, "Visa Type is auto poulated correctly after error handling of data mismatch in newly created Travel plan");
				screenShotAndInfoMsg(logger, driver, "visa type populated correctly");
			}
			scrollToElementToCenter(nav.label(driver, "Destination Office City", ""), driver);
			if (nav.text(driver, "Destination Office City", "").getAttribute("value").equals(PMGCity)) {
				logger.log(LogStatus.PASS, "Destination Office City field is auto populated correctly after error handling of data mismatch in newly created TP");
				screenShotAndInfoMsg(logger, driver, "City populated correctly");
			}
			DeletePMGCityAndStatesRecord();
			DeletePMGVisaTypeRecord();
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "generation of Mismatched Visa And City Names Failed");
			util.screenShotAndErrorMsg(logger, e, driver, "generation of Mismatched Visa And City Names Failed");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void DataMismatchUpdate() {
		ExtentTest logger = extent.startTest("Verify Updation of Process Types", "Verify Updation of Process Types");
		try {
			util.scrollByVisibleElement(driver, logger, nav.label(driver, "HRC", "HR Cases"));
			nav.tabName(driver, "Tasks").click();
			util.pause(logger, "2");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Search", "HR Tasks"), "Short description");
			util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", "HR Tasks"), "PMG GCP Data Mismatch");
			util.clickOn(logger, nav.tooltip(driver, "Preview", "", "HR Tasks"));
			util.pause(logger, "11");
			util.clickOn(logger, nav.link(driver, "Open Record", ""));
			util.pause(logger, "5");
			util.pause(logger, "15");
		//	ValidateWorkNotesActivityForVisaAndCity(false, true, "PMG GCP Data Mismatch");
			ValidateWorkNotesActivityForVisaAndCity(false, false, "PMG GCP Data Mismatch");
			screenShotFileName = screenShotPath + "DataMismatchUpdate " + arr1[0] + "_" + dateFormat.format(date) + "1"
					+ ".jpg";
			util.captureScreenShot(logger, driver, screenShotFileName);
			util.scrollByVisibleElement(driver, logger, portal.label(driver, "Activit"));
			screenShotFileName = screenShotPath + "DataMismatchUpdate " + arr1[0] + "_" + dateFormat.format(date) + "2"
					+ ".jpg";
			util.captureScreenShot(logger, driver, screenShotFileName);
		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL, "Eligibility Check For GCP HR Task is not closed");
		}
	}

	public void PostGCPCall(String ColumnName) {
		ExtentTest logger = extent.startTest("PostGCPCall", "Post GCP Call to create Travel plan.");
		try {
			AuthorizationToken = "Bearer " + token;
			DocumentID = generateUniqueDocumentIds(logger);
			RestAssured.baseURI = baseURI;
			String response = given().log().all().header("Authorization", AuthorizationToken)
					.header("Content-Type", ContentTypeJSON).body(callGCP_Payload(ColumnName, DocumentID)).when().post(ResourceURI)
					.then().log().all().extract().response().asString();

			System.out.println(response);

			JsonPath js = rawToJSON(response);
			System.out.println(js.getString("messageResponses[0]"));
			logger.log(LogStatus.INFO, "Result: " + response);
			if (response.contains("Record processed successfully")) {
				logger.log(LogStatus.PASS, "GCP Post api is successfull" + "/n" + response);
			}
		} catch (Exception e) {
			// TODO: handle exception
		}
	}

	@Test
	public void DeletePMGVisaTypeRecord() {
		ExtentTest logger = extent.startTest("Delete Visa Record",
				"Delete PMG Visa Type Record");
		try {
			    openPMGVisaTypesTable(logger);
				util.clickOn(logger, nav.tooltip(driver, "Show / hide filter", "", ""));
				util.pause(logger, "3");
				setFilterConditions(logger, "GCP Visa Type", "is", getInputData(TestName, "ProposedVisaType"), 1);
				util.pause(logger, "10");
				util.clickOn(logger, nav.tooltip(driver, "Run filter", "", ""));
				
				if (driver.findElements(By.xpath("//label[@class='checkbox-label']")).size() > 0) {
					util.clickOn(logger, driver.findElement(By.xpath("//label[@class='checkbox-label']")));
					Select dropDown = new Select(
							driver.findElement(By.xpath("//select[contains(@class,'list_action_option')]")));
					screenShotAndInfoMsg(logger, driver, "Filtered Visa Record");
					// changed
					util.clickOn(logger, dropDown.getFirstSelectedOption());
					util.clickOn(logger, portal.label(driver, "Delete"));
					
					util.pause(logger, "5");
					// clicking on delete button in pop-up
					util.clickOn(logger, driver.findElement(By.xpath("//*[@id='ok_button']")));
					driver.navigate().refresh();
					util.waitForPageToLoadCompletely(logger, driver);
				}
		} catch (Exception e) {

			util.screenShotAndErrorMsg(logger, e, driver, "unable to Delete PMG City And States Record");
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author k.p.balakrishnan
	 * @param Date
	 * @implNote Add test data as a row in the H1B_Information_12-13-2022 excel This
	 *           method is used to create H1B Travel plan via bulk upload Mandatory
	 *           data to be passed in excel: AdminEID, EntrepriseID
	 */
	@Parameters("Date")
	@Test
	public void createH1BTravelPlan(String Date) {
		ExtentTest logger = extent.startTest("PM Bulk Upload - Creating H1B Travel Plan",
				"PM Bulk Upload For Creating H1B Travel Plan");
		try {
			// loginAsTraveler(FulfillerEID);
			loginAsAdmin();
			navigateToNavPageFromPortal();
			util.waitForPageToLoadCompletely(logger, driver);
 
			List<String> item = new ArrayList<String>();
			item.add("People Mobility");
			item.add("Bulk Uploads");
			item.add("Bulk Upload - RP");
			shadowDomFilterSearch(logger, item.get(0), item, "Bulk Upload - RP");
 
			util.waitForPageToLoadCompletely(logger, driver);
			if (portal.label(driver, "People Mobility Bulk Upload").getText().contains("People Mobility Bulk Upload")) {
				logger.log(LogStatus.PASS, "Header is as expected");
			} else {
				logger.log(LogStatus.FAIL, "Header is not as Expected");
			}
			util.verifyElementByXpath(logger, portal.label(driver,
					"Create new records in the People Mobility Gateway for H1B , Tax Cost Estimates and Tax Information tables, in bulk."));
			util.selectBoxByValue(logger, portal.dropdown(driver, "Type of record to import"), "H-1B Cap Nominations");
			uploadAttachmentOnNavPage(logger, "H1B_Information_" + Date + ".xlsx");
 
			util.pause(logger, "5");
			util.clickOn(logger, portal.button(driver, "Submit"));
			util.waitForPageToLoadCompletely(logger, driver);
			isH1BTravelPlanCreated = true;
			logger.log(LogStatus.PASS, "H1B Travel Plan is created via bulk upload");
		} catch (Exception e) {
			// TODO: handle exception
			logger.log(LogStatus.FAIL, "H1B Travel Plan is not created via bulk upload");
			util.screenShotAndErrorMsg(logger, e, driver, "H1B Travel Plan is not created via bulk upload");
		}
		extent.endTest(logger);
		extent.flush();
	}

	/**
	 * @author k.p.balakrishnan This method used to get H1B Travel Plan Number and
	 *         will save it in the String H1BNominatedTravelPlanNumber.
	 */
	@Test
	public void getH1BTravelPlanInListView() {
		ExtentTest logger = extent.startTest("Get H1B Nominated Travel Plan Number",
				"Get H1B Nominated Travel Plan Number in list view");
		try {
			TestUser = getInputData(TestName, "TestUser");
			if (TestUser.contains("PMG FULFILLER")) {
				UserLoginAsFulfiller();
			}
			navigateToNavPageFromPortal();
			util.waitForPageToLoadCompletely(logger, driver);
			openH1BTravelPlanTable();
            util.pause(logger, "10");
            addColumn(logger, "Travel Plan Name");
            util.selectBoxByValue(logger, nav.dropdown(driver, "Search", ""), "Travel Plan Name");
            util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", ""), "*T39377.07");
            util.pause(logger, "3");
			sortColumn(logger, "Created", "Sort (z to a)", "");
			util.scrollByVisibleElement(driver, logger, nav.link(driver, "Number", ""));
			TravelPlanNumber = nav.getTableCellText(logger, driver, "Number", "");
			screenShotAndInfoMsg(logger, driver, "TP Number");
			System.out.println("TravelPlanNumber: " + TravelPlanNumber);
			logger.log(LogStatus.INFO, TravelPlanNumber);
			util.verifyElementByXpath(logger, nav.tooltip(driver, "Preview TRA", "", ""));
			
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Failed to get H1B Nominated Travel Plan Number");
			util.screenShotAndErrorMsg(logger, e, driver, "Failed to get H1B Nominated Travel Plan Number");
		}
		extent.endTest(logger);
		extent.flush();
	}
 
	@Test
	public void getH1BTravelPlanInFormView() {
		ExtentTest logger = extent.startTest("Get H1B Nominated Travel Plan Number",
				"Get H1B Nominated Travel Plan Number in form view");
		try {
			getH1BTravelPlanInListView();
			util.pause(logger, "3");
			util.clickOn(logger, nav.tooltip(driver, "Preview", "", ""));
			util.pause(logger, "5");
			util.clickOn(logger, nav.link(driver, "Open Record", ""));
			util.pause(logger, "5");
			System.out.println("Record: " + H1BNominatedTravelPlanNumber + " is opened");
			logger.log(LogStatus.PASS, "Record: " + H1BNominatedTravelPlanNumber + " is opened");
			util.clickOn(logger, nav.tabName(driver, "Main Details"));
			H1BNominatedTravelPlanName = util.getElementValue(logger,
					nav.text(driver, "Travel Plan Name", "Main Details"));
			if (H1BNominatedTravelPlanName.equals(null) || H1BNominatedTravelPlanName.equals("")) {
				logger.log(LogStatus.FAIL,
						H1BNominatedTravelPlanName + "  (H1B Nominated Travel plan number) is failed to fetched");
			} else {
				logger.log(LogStatus.PASS,
						H1BNominatedTravelPlanName + " (H1B Nominated Travel plan number) is fetched");
			}
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Failed to get H1B Nominated Travel Plan Number");
			util.screenShotAndErrorMsg(logger, e, driver, "Failed to get H1B Nominated Travel Plan Number");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void openH1BUserDataTable() throws AWTException {
		ExtentTest logger = extent.startTest("Open H1B User Data Table", "Open H1B User Data Table");
		try {
			browserHelper.navigateTo(logger, ADSSNowURL);
			List<String> item = new ArrayList<String>();
			item.add("People Mobility");
			item.add("H1B");
			item.add("PMG H1B User Data");
			shadowDomFilterSearch(logger, item.get(0), item, "PMG H1B User Data");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to Open the IRW Table");
		}
		extent.endTest(logger);
		extent.flush();
	}

	@Test
	public void openH1BTravelPlanTable() throws AWTException {
		ExtentTest logger = extent.startTest("Open H1B User Data Table", "Open H1B User Data Table");
		try {
			browserHelper.navigateTo(logger, ADSSNowURL);
			List<String> item = new ArrayList<String>();
			item.add("People Mobility");
			item.add("H1B");
			item.add("PMG H1B Travel Plan");
			shadowDomFilterSearch(logger, item.get(0), item, "PMG H1B Travel Plan");
		} catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to Open the IRW Table");
		}
		extent.endTest(logger);
		extent.flush();
	}
	@Test
	public void verifyEditabilityOfH1BMultiLocationFieldsInH1BUserDataTable() throws AWTException {
		ExtentTest logger = extent.startTest("verify Editability Of H1B Multi Location Fields In H1B User Data Table");
		try {
			addColumn(logger, "Travel Plan");
			util.pause(logger, "5");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Search", ""), "Travel Plan");
			util.setTextWithEnter(logger, nav.backgroundText(driver, "Search", ""), TravelPlanNumber);
			util.pause(logger, "4");
			String[] fields = {"Work Location 2","Address (including Zip code) 2","Percentage of time in work location 2","Work Location 3","Address (including Zip code) 3","Percentage of time in work location 3"};
			for(String str: fields)
			{
			nav.verifyTableElements(logger, str, "others", "");
			}
			editTableTextDropDown(logger, "Work Location 2", "Working in Accenture Office");
			editTableText(logger, "Address (including Zip code) 2", "Test");
			editTableTextDropDown(logger, "Percentage of time in work location 2", "5%");
			screenShotAndInfoMsg(logger, driver, "work location 2 related column view");
			editTableTextDropDown(logger, "Work Location 3", "Working at Other Location");
			editTableText(logger, "Address (including Zip code) 3", "Testing");
			editTableTextDropDown(logger, "Percentage of time in work location 3", "6%");
			screenShotAndInfoMsg(logger, driver, "work location 3 related column view");
			String number = nav.getTableCellText(logger, driver, "Number", "");
			//openRecord(logger, number, "Number");
			openRecord(logger, TravelPlanNumber, "Travel Plan");
			String[] changedValue = {"Working in Accenture Office","Test","5%","Working at Other Location","Testing","6%"};
			for(int i=0;i<6;i++)
			{
				verifyFieldsInActivitiesSection(logger, fields[i], changedValue[i]);
			}
			screenShotAndInfoMsg(logger, driver, "Activities tracked");
			scrollToElementToCenter(nav.dropdown(driver, "Work Location 2", ""), driver);
			util.selectBoxByValue(logger, nav.dropdown(driver, "Work Location 2", ""), "Working at Other Location");
			util.clearText(logger, nav.text(driver, "Address (including Zip code) 2", ""));
			util.setText(logger, nav.text(driver, "Address (including Zip code) 2", ""), "abc");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Percentage of time in work location 2", ""), "12%");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Work Location 3", ""), "Working in Accenture Office");
			util.clearText(logger, nav.text(driver, "Address (including Zip code) 3", ""));
			util.setText(logger, nav.text(driver, "Address (including Zip code) 3", ""), "xyz");
			util.selectBoxByValue(logger, nav.dropdown(driver, "Percentage of time in work location 3", ""), "12%");
			util.clickOn(logger, nav.button(driver, "Update", ""));
			//openRecord(logger, number, "Number");
			openRecord(logger, TravelPlanNumber, "Travel Plan");
			String[] changedValueAgain = {"Working at Other Location","abc","12%","Working in Accenture Office","xyz","12%"};
			for(int i=0;i<6;i++)
			{
				verifyFieldsInActivitiesSection(logger, fields[i], changedValueAgain[i]);
			}
			screenShotAndInfoMsg(logger, driver, "Activities tracked");
		}
		 catch (Exception e) {
			util.screenShotAndErrorMsg(logger, e, driver, "verify Editability Of H1B Multi Location Fields In H1B User Data Table");
		}
		extent.endTest(logger);
		extent.flush();
	}
	
	@Test
	public void openH1BUserDataRecord() {
		ExtentTest logger = extent.startTest("Open H1B user data record", "Open H1B User data record.");
		try {
			openH1BUserDataTable();
			// To filter travel plan
			openRecord(logger, H1BNominatedTravelPlanNumber, "Travel Plan");
			logger.log(LogStatus.PASS, H1BNominatedTravelPlanNumber + " Record is opened");
		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to open H1B user data record");
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to open H1B user data record");
		}
	}

	@Test
	public void creationOfGCPRecord() {
		ExtentTest logger = extent.startTest("Creation of GCP record.", "Creation of GCP record.");
		try {

			DocumentID = generateUniqueDocumentIds(logger);

			//Login as admin to access the REST API
			loginAsAdmin();
			browserHelper.navigateTo(logger, restAPI);
			util.waitForPageToLoadCompletely(logger, driver);
			util.pause(logger, "10");
			boolean isLabelDisplayed = false;

			// Access the API
			util.selectBoxByValue(logger, nav.dropdown(driver, "Namespace", ""), getInputData("navigate", "Namespace"));
			Thread.sleep(30000); // Initial wait time for page load

			// Continuously wait until 'EAM - Test REST API' label is displayed
			while (!isLabelDisplayed) {
				List<WebElement> labels = driver.findElements(By.xpath("//span//b[text()='EAM - Test REST API']"));
				if (!labels.isEmpty()) {
					System.out.println("Label 'EAM - Test REST API' found. Proceeding to select 'dataFabric_adapter' in API Name dropdown.");
					isLabelDisplayed = true;
					util.selectBoxByValue(logger, nav.dropdown(driver, "API Name", ""), "dataFabric_adapter");
				} else {
					System.out.println("Label 'EAM - Test REST API' not yet available... Waiting for 10 seconds.");
					Thread.sleep(10000); // Pause for 10 seconds before checking again
				}
			}

			util.pause(logger, "10");
			util.clickOn(logger, driver.findElement(By.xpath("//*[@id='raw']")));
			util.pause(logger, "10");
			util.setText(logger, driver.findElement(By.xpath("//*[@id='post_body_ta']")), callGCP_Payload(DocumentID));
			util.pause(logger, "5");
			util.clickOn(logger, nav.button(driver, "Send", ""));

			//Accept alert message
			try {
				Thread.sleep(2000); 
				Alert alert = driver.switchTo().alert(); 
				System.out.println("Alert Message: " + alert.getText()); 
				alert.accept(); 
				System.out.println("Alert closed successfully! Record is created.");
				logger.log(LogStatus.PASS, "GCP record is created successfully.");
			} catch (Exception e) {
				System.out.println("No alert found.");
			}

			System.out.println(DocumentID);

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to create GCP record");
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to create GCP record");
		}
	}

	@Test
	public void updateOfGCPRecord() {
		ExtentTest logger = extent.startTest("Update of GCP record.", "Update of GCP record.");
		try {

			//Login as admin to access the REST API
			loginAsAdmin();
			browserHelper.navigateTo(logger, restAPI);
			util.waitForPageToLoadCompletely(logger, driver);
			util.pause(logger, "10");
			boolean isLabelDisplayed = false;

			// Access the API
			util.selectBoxByValue(logger, nav.dropdown(driver, "Namespace", ""), getInputData("navigate", "Namespace"));
			Thread.sleep(30000); // Initial wait time for page load

			// Continuously wait until 'EAM - Test REST API' label is displayed
			while (!isLabelDisplayed) {
				List<WebElement> labels = driver.findElements(By.xpath("//span//b[text()='EAM - Test REST API']"));
				if (!labels.isEmpty()) {
					System.out.println("Label 'EAM - Test REST API' found. Proceeding to select 'dataFabric_adapter' in API Name dropdown.");
					isLabelDisplayed = true;
					util.selectBoxByValue(logger, nav.dropdown(driver, "API Name", ""), "dataFabric_adapter");
				} else {
					System.out.println("Label 'EAM - Test REST API' not yet available... Waiting for 10 seconds.");
					Thread.sleep(10000); // Pause for 10 seconds before checking again
				}
			}

			util.pause(logger, "10");
			util.clickOn(logger, driver.findElement(By.xpath("//*[@id='raw']")));
			util.pause(logger, "10");
			util.setText(logger, driver.findElement(By.xpath("//*[@id='post_body_ta']")), callGCP_Payload("Payload2", DocumentID));
			util.pause(logger, "5");
			util.clickOn(logger, nav.button(driver, "Send", ""));

			//Accept alert message
			try {
				Thread.sleep(2000); 
				Alert alert = driver.switchTo().alert(); 
				System.out.println("Alert Message: " + alert.getText()); 
				alert.accept(); 
				System.out.println("Alert closed successfully! Record is created.");
				logger.log(LogStatus.PASS, "GCP record is created successfully.");
			} catch (Exception e) {
				System.out.println("No alert found.");
			}

			System.out.println(DocumentID);

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to create GCP record");
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to create GCP record");
		}
	}

	@Test
	public void updateExistingGCPRecord() {
		ExtentTest logger = extent.startTest("Update of GCP record.", "Update of GCP record.");
		try {

			//Login as admin to access the REST API
			loginAsAdmin();
			browserHelper.navigateTo(logger, restAPI);
			util.waitForPageToLoadCompletely(logger, driver);
			util.pause(logger, "10");
			boolean isLabelDisplayed = false;

			// Access the API
			util.selectBoxByValue(logger, nav.dropdown(driver, "Namespace", ""), getInputData("navigate", "Namespace"));
			Thread.sleep(30000); // Initial wait time for page load

			// Continuously wait until 'EAM - Test REST API' label is displayed
			while (!isLabelDisplayed) {
				List<WebElement> labels = driver.findElements(By.xpath("//span//b[text()='EAM - Test REST API']"));
				if (!labels.isEmpty()) {
					System.out.println("Label 'EAM - Test REST API' found. Proceeding to select 'dataFabric_adapter' in API Name dropdown.");
					isLabelDisplayed = true;
					util.selectBoxByValue(logger, nav.dropdown(driver, "API Name", ""), "dataFabric_adapter");
				} else {
					System.out.println("Label 'EAM - Test REST API' not yet available... Waiting for 10 seconds.");
					Thread.sleep(10000); // Pause for 10 seconds before checking again
				}
			}

			util.pause(logger, "10");
			util.clickOn(logger, driver.findElement(By.xpath("//*[@id='raw']")));
			util.pause(logger, "10");
			util.setText(logger, driver.findElement(By.xpath("//*[@id='post_body_ta']")), callGCP_Payload("Payload3", DocumentID));
			util.pause(logger, "5");
			util.clickOn(logger, nav.button(driver, "Send", ""));

			//Accept alert message
			try {
				Thread.sleep(2000); 
				Alert alert = driver.switchTo().alert(); 
				System.out.println("Alert Message: " + alert.getText()); 
				alert.accept(); 
				System.out.println("Alert closed successfully! Record is created.");
				logger.log(LogStatus.PASS, "GCP record is created successfully.");
			} catch (Exception e) {
				System.out.println("No alert found.");
			}

			System.out.println(DocumentID);

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to create GCP record");
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to create GCP record");
		}
	}

	@Test
	public void openTravelPlanInTheDashboard() {
		ExtentTest logger = extent.startTest("Traveler opens the travel plan in the dashboard.", "Traveler opens the travel plan in the dashboard.");
		try {

			//Login as Traveler
			UserLoginAsTraveler();
			util.waitForPageToLoadCompletely(logger, driver);
			WebElement hidebutton = driver.findElement(By.xpath("//button[@id='dummyfooter']"));
			util.clickOn(logger, hidebutton);	

			WebElement horizontalScroll = driver.findElement(By.xpath("//div[@class='travel-plan-section']"));					
			((JavascriptExecutor) driver).executeScript("arguments[0].scrollIntoView(true);", horizontalScroll);
			
			// Find the travel Plan
			boolean isFound = false;
			while (!isFound) {
				List<WebElement> travelPlanNumbers = driver.findElements(By.xpath("//*[@class='travel-plan-number ng-binding']"));
				for (WebElement travelPlanNumber : travelPlanNumbers) {
					if (travelPlanNumber.getText().equals(TravelPlanNumber)) {
						logger.log(LogStatus.PASS, "Travel Plan ID: " + TravelPlanNumber + " is found.");
						isFound = true;
						break;
					}
				}
				if (!isFound) {
					((JavascriptExecutor) driver).executeScript("arguments[0].scrollLeft += 200;", horizontalScroll);
					util.pause(logger, "2");
				}
			}

			WebElement travelPlanTile = driver.findElement(By.xpath("//*[text()='" + TravelPlanNumber + "']/parent::h4/parent::div/../..//div//img[@class='card-img-top']"));
			util.clickOn(logger, travelPlanTile);
			logger.log(LogStatus.PASS, "Travel plan is opened in the dashboard.");
			System.out.println("Travel plan is opened in the dashboard.");

			util.waitForPageToLoadCompletely(logger, driver);
			util.pause(logger, "15");
			WebElement keyInfo = driver.findElement(By.xpath("//h3[text()='Key information']"));
			util.scrollByVisibleElement(driver, logger, keyInfo);
			util.waitForPageToLoadCompletely(logger, driver);
			util.pause(logger, "15");
			WebElement clickTask = driver.findElement(By.xpath("//a[@aria-label='See tasks']"));
			util.clickOn(logger, clickTask);
			logger.log(LogStatus.PASS, "Traveler clicked on the task.");

		} catch (Exception e) {
			logger.log(LogStatus.FAIL, "Unable to open the travel plan in the dashboard.");
			util.screenShotAndErrorMsg(logger, e, driver, "Unable to open the travel plan in the dashboard.");
		}
	}


}
