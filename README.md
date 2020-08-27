# Antiforgery
Token Issue project


steps:

run the api  and run the angular project.

Reproduce issue.

Once login, it will show the dashboard.

click on the message menu in UI, It will send X-XSRF token to the APi method.


file is user.service.ts in angular

getMessages(id: number, page?, itemsPerPage?, messageContainer?) {

Webapi

Message controller.cs

        [HttpGet]
        [ValidateAntiForgeryToken]
        public async Task<IActionResult> GetMessagesForUser (int userId, [FromQuery] MessageParams messageParams)
           {
          

Note:
I have added xsrf token only for this request for testing purpose.

I am testing with Get Request not post.

[AutoValidateAntiforgeryToken] will ignore get,patch,options,trace.

