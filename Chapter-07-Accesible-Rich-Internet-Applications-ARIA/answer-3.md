#### Describe what accessibility is and explain why it is important for web applications to be accessible.

# Accessibility in Web Development - ARIA

Not everybody out there is able to use a pointing device, read a low contrast text or even read on a screen. Making a web accessible to all those people is fair with them and makes our audience wider.

## Diversity of Web Users

There is a wide range of people facing web accessibility barriers from poorly designed websites with no accessibility in mind. Some of the most common disabilities and its barriers[1] include:

| Disability | Description | Barriers |
| :------------- | :------------- | :-------- |
| Auditory | Mild or moderate hearing impairments in one or both ears | Audio content without captions, media players without volume controls or applications relying on voice interaction only |
| Cognitive and neurological | Disorders of any part of the nervous system impacting how people hear, move or understand information. It does not necessarily affect intelligence | Complex navigation mechanisms, complex sentences, long passages of text or background audio that cannot be turned off |
| Physical | Weakness, muscular control limitations, limitations of sensations, pain that impedes movement or missing limbs | Sites not providing full keyboard support, insufficient time to complete tasks, no text alternatives to media or complex navigation mechanisms |
| Speech | Difficulties producing a recognizable speech | Applications relying on voice interaction only or websites which offer phone numbers as the only communication option |
| Visual | Mild or moderate hearing impairments in one or both eyes | Visual media with no text alternatives, text or layouts that cannot be resized, insufficient contrast between foreground and background or tools that do not provide full keyboard support |

## ARIA

WAI-ARIA (*Web Accessibility Initiative – Accessible Rich Internet Applications*) is a [W3C](https://www.w3.org/) specification which defines a way to increase the accessibility of web pages content. Its main focus is dynamic content and advanced user interface controls, such as those developed with Ajax or JavaScript and how to provide the necessary information to assistive technologies.

WAI-ARIA defines HTML attributes to provide HTML widgets with semantics and metadata. The specification defines a wide range of attributes, from roles that specify the type of widget presented, to properties describing the state of the widget or the relationships between its elements. Assistive technologies such as screen readers can take advantage of this information to provide accessible experience to people with disabilities.

WAI-ARIA provides an extensive documentation. Some of the most interesting links follows:

- [WAI-ARIA Authoring Practices](https://www.w3.org/TR/wai-aria-practices-1.1/)
- [The Roles Model](https://www.w3.org/TR/wai-aria/roles)
- [Supported States and Properties](https://www.w3.org/TR/wai-aria/states_and_properties)

## Conclusion

The Web is reaching many important aspects of life, such as bureaucracy, education, commerce or health care. And it has the potential to provide equal access and equal opportunity to people with disabilities as never before. It is our duty as web developers to no waste this opportunity.

### References

1. [Diversity in Web Use](https://www.w3.org/WAI/intro/people-use-web/browsing)

---

Carlos Coves Prieto

11/07/2016

Career Path 3: Modern Frontend Developer
