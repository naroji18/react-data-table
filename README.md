# add this component and import it

    <DataTable columns={columns} data={data} onView={handleView} onEdit={handleEdit} onDelete={handleDelete} />


## same object is need in columns

 const columns = useMemo(
    () => [
      {
        Header: 'ID',
        accessor: 'id',
        Filter: ColumnFilter,
      },
      {
        Header: 'Name',
        accessor: 'name',
        Filter: ColumnFilter,
      },
      {
        Header: 'Age',
        accessor: 'age',
        Filter: ColumnFilter,
      },
      {
        Header: 'Country',
        accessor: 'country',
        Filter: ColumnFilter,
      },
    ],
    []
  );


### data to show in table

const initialData = [
    { id: 1, name: 'John Doe', age: 28, country: 'USA' },
    { id: 2, name: 'Jane Doe', age: 29, country: 'UK' },
    { id: 3, name: 'Jack Smith', age: 35, country: 'Canada' },
    // More data...
  ];

  const [data, setData] = useState(initialData);



### function to handle button edit and 

const handleView = (row) => {
    alert(`Viewing: ${JSON.stringify(row, null, 2)}`);
  };

  const handleEdit = (row) => {
    alert(`Editing: ${JSON.stringify(row, null, 2)}`);
  };

  const handleDelete = (row) => {
    alert(`Deleting: ${JSON.stringify(row, null, 2)}`);
    const filteredData = data.filter((item) => item.id !== row.id);
    setData(filteredData);
  };


