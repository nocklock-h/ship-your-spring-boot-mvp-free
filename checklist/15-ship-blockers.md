# 15 Spring Boot MVP Ship Blockers

Your application works on localhost.

Before you ship it, check these 15 blockers.

If any critical item fails, fix it before going live.

---

## 1. Clean Build Works

- [ ] The project builds successfully from a clean state.

### Verify

```bash
./gradlew clean build

Windows:

gradlew.bat clean build
Pass condition

The build completes without errors.

2. Automated Tests Pass
 Existing automated tests pass before deployment.
Verify
./gradlew test
Pass condition

No failing tests.

3. Production Configuration Is Separated
 Production configuration does not depend on local-only values.

Check:

Database URLs
API URLs
File paths
Active Spring profiles
Debug settings
Watch for
localhost
127.0.0.1
C:\...
/Users/...

These often work locally and fail after deployment.

4. Secrets Are Not Hardcoded
 Passwords, API keys, tokens, and private credentials are not committed to Git.

Check:

application.yml
application.properties
Java source files
JavaScript files
Docker files
CI/CD configuration
Never commit
Database passwords
API keys
JWT secrets
Cloud credentials
Private tokens

Use environment variables instead.

5. Required Environment Variables Exist
 Every required production environment variable is configured.

Examples:

DATABASE_URL
DATABASE_USERNAME
DATABASE_PASSWORD
API_KEY
SPRING_PROFILES_ACTIVE
Pass condition

The application starts without falling back to unintended local values.

6. Database Configuration Works in Production
 The deployed application can successfully connect to its production database.

Verify:

Connection URL
Username/password
SSL requirements
Connection pool settings
Schema initialization or migrations
Pass condition

The application boots and performs a real database read/write successfully.

7. External Services Work Outside Localhost
 Every external dependency works from the deployed environment.

Examples:

AI APIs
Email providers
Object storage
Payment APIs
External REST APIs
Pass condition

The production server can reach each required service.

8. User Input Is Validated
 User-controlled input is validated before processing.

Check:

Request bodies
Query parameters
Path variables
Form inputs
Uploaded filenames
Goal

Do not assume client-side validation is enough.

9. Errors Do Not Expose Internal Details
 Production errors do not expose stack traces or sensitive implementation details.

Avoid returning:

Database credentials
Internal file paths
Stack traces
SQL queries
Server configuration
Pass condition

Users receive safe error responses while useful details remain in server logs.

10. Authentication and Authorization Are Checked
 Protected endpoints cannot be accessed without the required permissions.

Test:

Unauthenticated requests
Expired credentials
Invalid credentials
Access to another user's resources

If your MVP has no authentication, mark this item as N/A.

11. CORS Is Not Accidentally Wide Open
 Production CORS settings allow only the origins your application actually needs.

Review configurations such as:

allowedOrigins("*")
Goal

Do not leave development-only CORS settings enabled without understanding the impact.

12. File Uploads Are Validated

If your application accepts files:

 File size is limited
 File type is validated
 Unexpected files are rejected
 User filenames are not blindly trusted

If your MVP does not accept uploads, mark this item as N/A.

13. Logs Do Not Leak Sensitive Data
 Production logs do not contain secrets or unnecessary personal information.

Check for:

Passwords
Authorization headers
API keys
Access tokens
Personal data
Full request bodies

Log what you need to debug — not everything you receive.

14. The Production Start Process Works
 The application can start using the same command and configuration used in production.

Verify:

Java version
Port configuration
Start command
Docker configuration, if used
Required environment variables
Pass condition

The application boots successfully in the actual deployment environment.

15. Critical User Flow Works After Deployment
 The most important user flow has been tested against the deployed application.

Example:

Open application
↓
Submit input
↓
Backend processes request
↓
Database / external service responds
↓
User receives expected result

Do not stop testing just because deployment says:

SUCCESS

Deployment success does not guarantee application success.

Final Check

Before shipping:

[ ] Clean build
[ ] Tests pass
[ ] Production config verified
[ ] No hardcoded secrets
[ ] Environment variables configured
[ ] Database verified
[ ] External services verified
[ ] Input validation checked
[ ] Error exposure checked
[ ] Authentication / authorization checked
[ ] CORS checked
[ ] File uploads checked
[ ] Logs checked
[ ] Production startup verified
[ ] Critical user flow smoke-tested
Rule

If you cannot explain why an item is safe to ignore, do not ignore it.

This is the Free Edition of Ship Your Spring Boot MVP.

The Full Edition expands these checks into detailed verification steps, AI-assisted reviews, security checks, deployment workflows, and production-readiness templates.

Built by Nocklock.
