{% Original %}  

 let bookings = '';

    fetch("{% url 'bookings' %}" + '?date=' + date)
      .then(r => r.json())
      .then(data => {
        reserved_slots = [];
        bookings = '';
        console.log(data);
      });

        /* Step 11: Part three */
        for (let i = 0; i < data.length; i++) {
          let item = data[i];
          console.log(item.fields);
          reserved_slots.push(item.fields.reservation_slot);
          bookings = (`<p>${item.fields.first_name} - ${formattime(item.fields.reservation_slot)}</p>`);
        }



{% Updated %}


fetch("{% url 'bookings' %}" + '?date=' + date)
  .then(r => r.json())
  .then(data => {
    console.log(data);
    
    // Additional processing using 'data'
    for (let i = 0; i < data.length; i++) {
      let item = data[i];
      console.log(item.fields);
      reserved_slots.push(item.fields.reservation_slot);
      bookings += `<p>${item.fields.first_name} - ${formattime(item.fields.reservation_slot)}</p>`;   {% booking has += instead of =     The parenthesis are gone%}
    }

    // Now, 'reserved_slots' and 'bookings' are updated
  });                                                                 {% curly and parenthesis are added with a closing semicolon %}