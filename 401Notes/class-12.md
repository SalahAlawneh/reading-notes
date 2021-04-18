# Spring RESTful Routing & Static Files
- ` @RequestMapping` manage all type of requests in spring
- we can do it by:
   - by Path
   - the HTTP Method
- RequestMapping and HTTP Headers:
   - @RequestMapping With the headers Attribute
   - @RequestMapping Consumes and Produces
- RequestMapping With Path Variables:
   - Single @PathVariable
   - Multiple @PathVariable
   - @PathVariable With Regex
- RequestMapping With Request Parameters:(ie)
```
@RequestMapping(value = "/ex/bars", method = GET)
@ResponseBody
public String getBarBySimplePathWithRequestParam(
  @RequestParam("id") long id) {
    return "Get a specific Bar with id=" + id;
}
```
- RequestMapping Corner Cases:
   - @RequestMapping — Multiple Paths Mapped to the Same Controller Method
   - @RequestMapping — Multiple HTTP Request Methods to the Same Controller Method
   - @RequestMapping — a Fallback for All Requests
   - Ambiguous Mapping Error
***In general @RequestMapping as i conclude from my reading so stragiht forward, only callenge there is about the syntac and the ability to find the solution as fast as possible***
- Spring Data JPA store and retrive relational data bases.
- JPA stantds for=> Java Presistance API
- spring data repository interfaces:
    - CrudRepository: had almosst every thing you need in your application as you can see from the `CRUD` name you can know that it could do what i want in backend
    - PagingAndSortingRepository: {Page size,Current page number,Sorting}
    - JpaRepository: it have all of methods in the previous interfaces

- of course these repositories have there down side.
-  JpaRepository inherit every feature in  CrudRepository and PagingAndSortingRepository.