function initialName() {
    $('#filters-names .search_form input').val('Борщ')
};
initialName();

function initialCategories(){
  var category = 2,
      subcategory = 2,
      categoryItem = 3;
  // Set values
  $('select[name="category"]').prop('selectedIndex', category).selectric('refresh');
  $('select[name="subcategory"]').prop('disabled', false).prop('selectedIndex', subcategory).selectric('refresh');
  $('select[name="category-item"]').prop('disabled', false).prop('selectedIndex', categoryItem).selectric('refresh');

  // Get selectedIndex value
  $('select[name="category"]').on('selectric-close', function(e){
      var data = $(this).data('selectric');
      var selectedIndexValue = $(data.element).closest('.' + data.classes.wrapper).find('.selectric-items').find('li.selected').attr('data-index');
  });
};
initialCategories();
