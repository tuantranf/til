## RedirectAttributes: addAttribute vs addFlashAttribute

RedirectAttributes parameter and populate it with attributes for when the request get redirected, eg:
```
@RequestMapping(value="/hello", method=GET)
public String hello(RedirectAttributes redirAttr)
{
   // should I use redirAttr.addAttribute() or redirAttr.addFlashAttribute() here ?

   // ...

   return "redirect:/somewhere";
}
```

### addFlashAttribute
Actually stores the attributes in a flashmap (which is internally maintained in the users session and removed once the next redirected request gets fulfilled)

### addAttribute
Essentially constructs request parameters out of your attributes and redirects to the desired page with the request parameters.

### So the advantage
will be that you can store pretty much any object in your flash attribute(as it is not serialized into request params at all, but maintained as an object), whereas with addAttribute since the object that you add gets transformed to a normal request param, you are pretty limited to the object types like String or primitives.

[RedirectAttributes: addAttribute vs addFlashAttribute](http://stackoverflow.com/questions/14470111/spring-redirectattributes-addattribute-vs-addflashattribute)
