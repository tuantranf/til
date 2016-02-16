How to pass parameters to redirect page in spring-mvc

When the return value contains redirect: prefix, the viewResolver recognizes this as a special indication that a redirect is needed. The rest of the view name will be treated as the redirect URL. And the client will send a new request to this redirect URL. So you need to have a handler method mapped to this URL to process the redirect request.

You can write a handler method like this to handle the redirect request:
```
@RequestMapping(value="/home", method = RequestMethod.GET )
public String showHomePage(ModelMap model)  {
    String message = (String)model.get("message");
    model.addAttribute("message", message);
    return "home";
}
```
And you can re-write the logOut handler method as this:
```
@RequestMapping(value="/logOut", method = RequestMethod.POST )
public String logOut(Model model, RedirectAttributes redirectAttributes)  {
    redirectAttributes.addFlashAttribute("message", "success logout");
    System.out.println("/logOut");
    return "redirect:/home";
}
```

