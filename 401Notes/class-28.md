# RecyclerView
- to make sure not to confuse the RecyclerView can be in two context:
   - object
   - library
here we talk about the ojbject
- the RecyclerView make it easy to show a large amount of data
- from the name you can understand there is something recyled, wich is the single elements, so when the user scroll throw the application the view will not destroy, it will recycle to have the new content wich make it more efficient, and less consuming
- the RecyclerView can manage to display the data and how it's look like.
- and it's create the element dynamically, when it's needed
## Key classes
- ViewGroup => contain the views for my data
- view holder => the view for every element without any data, after createing the view the RecyclerView will bind it
- Adapter => the RecyclerView will call methods from Adapter to bind the data to view after requesting the views
- layout manager  => arrange the individual element in the list

## Steps for implementing your RecyclerView
1. decide the grid sytem you want to have in the your view
1. decide how the every single element how will look like and how it will behave, and extend the ViewHolder after that
1. Define the Adapter which is make the association between the data and the ViewHolder

## Plan your layout
the RecyclerView managed my LayoutManager, which have three classed to manage it:   
   1. LinearLayoutManager => One Dimention
   1. GridLayoutManager => Two Dimention
   1. StaggeredGridLayoutManager => Two Dimention, but the the height and width not have to be the same not for rows and not for columns

## Implementing your adapter and view holder
`binding`=> is the process will do the association between the data and it's view    
in order to do the binding with the Adapter you have to override these three methods:
- onCreateViewHolder()
- onBindViewHolder()
- getItemCount()
typical example=>
```

public class CustomAdapter extends RecyclerView.Adapter<CustomAdapter.ViewHolder> {

    private String[] localDataSet;

    /**
     * Provide a reference to the type of views that you are using
     * (custom ViewHolder).
     */
    public static class ViewHolder extends RecyclerView.ViewHolder {
        private final TextView textView;

        public ViewHolder(View view) {
            super(view);
            // Define click listener for the ViewHolder's View

            textView = (TextView) view.findViewById(R.id.textView);
        }

        public TextView getTextView() {
            return textView;
        }
    }

    /**
     * Initialize the dataset of the Adapter.
     *
     * @param dataSet String[] containing the data to populate views to be used
     * by RecyclerView.
     */
    public CustomAdapter(String[] dataSet) {
        localDataSet = dataSet;
    }

    // Create new views (invoked by the layout manager)
    @Override
    public ViewHolder onCreateViewHolder(ViewGroup viewGroup, int viewType) {
        // Create a new view, which defines the UI of the list item
        View view = LayoutInflater.from(viewGroup.getContext())
                .inflate(R.layout.text_row_item, viewGroup, false);

        return new ViewHolder(view);
    }

    // Replace the contents of a view (invoked by the layout manager)
    @Override
    public void onBindViewHolder(ViewHolder viewHolder, final int position) {

        // Get element from your dataset at this position and replace the
        // contents of the view with that element
        viewHolder.getTextView().setText(localDataSet[position]);
    }

    // Return the size of your dataset (invoked by the layout manager)
    @Override
    public int getItemCount() {
        return localDataSet.length;
    }
}


```
for more details ==>
***[Advanced RecyclerView customization](https://developer.android.com/guide/topics/ui/layout/recyclerview-custom)***