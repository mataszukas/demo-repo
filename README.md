**SKAITYMO LOGIKA:**
                  def read_csv(file_path):
                      item = {}
                      with open(file_path, mode='r') as file:
                          csv_reader = csv.DictReader(file)
                          for row in csv_reader:
                              item[row['name']] = {
                                  'category': row['category'],
                                  'price': row['price'],
                                  'stock_left': row['stock_left']                
                              }
                      return item
        
**RASYMO LOGIKA**
                  def write_csv(file_path, item_list):
                      with open(file_path, mode='w', newline='') as file:
                          fieldnames = ['name', 'category', 'price', 'stock_left']
                          writer = csv.DictWriter(file, fieldnames=fieldnames)
                          writer.writeheader()
                          for item_name, item_data in item_list.items():
                              row = {'name': item_name}
                              row.update(item_data)
                              writer.writerow(row)
