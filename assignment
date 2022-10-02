# steeleye-frontend-assignment
**1. Explain what the simple List component does.**

A) List component in the code is used to display the list of items stored in an array in an unordered list. When you click on the index of text of the items color changes to red i.e handleClick() function is implemented.

**2. What problems / warnings are there with code?**

A) useState hooks had no initial state value which went into syntax error.
const [selectedIndex,setSelectedIndex] = useState(false);
isSelected can be True or False

Variable with array value is default propsType value is Array
WrappedListComponent.defaultProps = { items: Array, };

index andisSelectedshould be used mandatory.

WrappedSingleListItem.propTypes = { index: PropTypes.number.isRequired, isSelected: PropTypes.bool.isRequired, onClickHandler: PropTypes.func.isRequired, text: PropTypes.string.isRequired, };

**3.Please fix, optimize, and/or modify the component as much as you think is necessary.**
```import React, { useState, useEffect, memo } from 'react';
import PropTypes from 'prop-types';

// Single List Item
const WrappedSingleListItem = ({
index,
isSelected,
onClickHandler,
text,
}) => {
return (
<li
style={{ backgroundColor: isSelected ? 'green' : 'red'}}
onClick={onClickHandler(index)}
>
{text}

);
};

WrappedSingleListItem.propTypes = {
index: PropTypes.number.isRequired,
isSelected: PropTypes.bool.isRequired,
onClickHandler: PropTypes.func.isRequired,
text: PropTypes.string.isRequired,
};

const SingleListItem = memo(WrappedSingleListItem);

// List Component
const WrappedListComponent = ({
items,
}) => {
const [selectedIndex,setSelectedIndex] = useState(false);

useEffect(() => {
setSelectedIndex(false);
}, [items]);

const handleClick = index => {
setSelectedIndex(index);
};

return (
<ul style={{ textAlign: 'left' }}>
{items.map((item, index) => (
<SingleListItem
key={index}
onClickHandler={() => handleClick(index)}
text={item.text}
index={index}
isSelected={selectedIndex}
/>
))}

)
};

WrappedListComponent.propTypes = {
items: PropTypes.array(PropTypes.shape({
text: PropTypes.string.isRequired,
})),
};

WrappedListComponent.defaultProps = {
items: [{ text: "First Item" }, { text: "Second Item" }],
};

const List = memo(WrappedListComponent);

export default List;
```
