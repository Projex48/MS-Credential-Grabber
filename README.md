# MS-Credential-Grabber
** POTENTIALLY UNWANTED PROGRAM **
DISCLAIMER: 
THIS PROGRAM IS STRICLY FOR EDUCATIONAL AND PENETRATION TESTING PURPOSES. ANY USE OF THIS REPOSITORY TO COLLECT USER DATA DIRECTLY VIOLATES THE ANTI-PHISHING ACT: 2005, 109th Congess S.472. 

## CREDIT: ##
I'd like to credit Ian Oister, Zac Tawfick, and Zane Weaver for helping to find the exploit in JAMF and Microsoft Identity Services.

## DISCLAIMER ##
While this repository does NOT collect user information, it shows how easily the user information could be collected.
Given the potential target of this vulnerability, potential damages range anywhere from a simple password change up to hundreds of thousands of dollars.

## STEPS TO REPRODUCE ##
PREREQ: This vulnerability requires a device running Jamf for authentication, configured to login using office.com or the standard microsoft login page.

PREREQ 2: We are currently on the JAMF authentication using the office login on the device.

PREREQ 3: Look for the "Sign-in options" button below the main login container. If it is not visible, click on the icon to change to local login and then again to go back to the microsoft login

Step 1: Click on "Sign-in options", verify that the "Sign-in options" container has been opened and has the "Sign in with GitHub" option.

Step 2: Click "Sign in with GitHub", verify that the GitHub login page and has the "Forgot password?" option.

Step 3: Click "Forgot password?", observe that the Forgot password page is open.

Step 4: Scroll down to the bottom of the page, verify that the Contact GitHub Support button is present.

Step 5: Click "Contact GitHub Support", verify that the GitHub Support page is present.

Step 6: Scroll down to the bottom of the page, verify that the GitHub icon is present in the bottom right of the page.

Step 7: Click on the GitHub icon, verify that you are on the GitHub home page.

Step 8: Use the search feature in GitHub to bring up this repo, verify that you are on this repository page.

Step 9: Click on this link: https://projex48.github.io/MS-Credential-Grabber/

The device is now on a microsoft login page made to look identical to the university that I currently attend. While this could be changed to represent that standard microsoft login page, this works for demonstration purposes.

## IDEAS FOR RESOLUTION ##
When developing and exploring this vulnerability, the question arose of how this vulnerability could be fixed. The following are several ideas we had, each based on the security issues we found within the various apps.

- JAMF Address Fencing: Given that the option to sign in with GitHub may be convenient for many users, we believe that it is unlikely that Microsoft would like to remove this option. Therefore, we thought that it would be a better option for JAMF to have a file of whitelisted pages that the authentication container should be allowed to visit.

- Chromium Kiosk Mode Dangerous Page Warning: While Chrome will display a warning when you are on a page that is likely to contain phishing, Chromium does not! Adding a warning may help prevent end-users from entering their information into phishing pages.

- GitHub Link change on GitHub Support: Changing the link that the GitHub icon in the bottom right of the GitHub support page to link to GitHub support would prevent users from being able to look up GitHub repositories. This change seems less feasible than the prior as there are many pages that the user has access to from the Sign in with GitHub option. It is likely that another page contains some link to the GitHub home page.