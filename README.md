# restock-shopping-cart
MIT xPro Week 19 - Assignment

### Video 19-5  Shopping Cart Exercise - Refactor Restocking Functionality

Product Web Component

If restocked, then the ```{list}``` needs to hav the new products.

The form to restock the products. onSubmit, call restockProducts from the strapi database with ```/${query}```

restockProduct function is called by the onsubmit event which provides the url. The doFetch function sets the URL with useState. When the useState is changed, it triggers the fetch. ```data``` is the array of new products. Use map to pick out each item of the products. Desctructure ```let { name, country, cost, instock } = item``` to limit the items to name, country, cost, instock as a new object. To setItems, spread the existing items and add the newItems. ```setItems([...items, ...newItems])``` When setItems is changed, the items are changed. The next time the list of items is rendered, the list function returns the product image, button with item name and cost, submit with item name with an onClick event to call addToCart. Change so that they are randomly accessed from picsum.

What is doFetch? Is it a function? Where and how is it defined?

```
const restockProducts = (url) => {
    doFetch(url);
    let newItems = data.map((item) => {
      let { name, country, cost, instock } = item;
      return { name, country, cost, instock };
    });
    setItems([...items, ...newItems]);
  };
```
Fetch from the useDataApi function useEffect. It is called when we change the url because it is told to track the url and fetch data when it changes.
