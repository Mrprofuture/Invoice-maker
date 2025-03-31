from flask import Flask, render_template_string, request, send_file
from reportlab.lib.pagesizes import letter
from reportlab.pdfgen import canvas

app = Flask(__name__)

class InvoiceMaker:
    def __init__(self, shop_name, shop_address, shop_phone):
        self.shop_name = shop_name
        self.shop_address = shop_address
        self.shop_phone = shop_phone

    def create_invoice(self, customer_name, customer_address, items, invoice_number, output_filename):
        c = canvas.Canvas(output_filename, pagesize=letter)
        width, height = letter

        # Shop details
        c.setFont("Helvetica-Bold", 12)
        c.drawString(50, height - 50, self.shop_name)
        c.setFont("Helvetica", 10)
        c.drawString(50, height - 70, self.shop_address)
        c.drawString(50, height - 90, f"Phone: {self.shop_phone}")

        # Customer details
        c.setFont("Helvetica-Bold", 12)
        c.drawString(50, height - 130, "Customer:")
        c.setFont("Helvetica", 10)
        c.drawString(50, height - 150, customer_name)
        c.drawString(50, height - 170, customer_address)

        # Invoice details
        c.setFont("Helvetica-Bold", 12)
        c.drawString(400, height - 50, f"Invoice #{invoice_number}")

        # Table header
        c.setFont("Helvetica-Bold", 10)
        c.drawString(50, height - 200, "Item")
        c.drawString(300, height - 200, "Quantity")
        c.drawString(400, height - 200, "Price")
        c.drawString(500, height - 200, "Total")

        # Table content
        c.setFont("Helvetica", 10)
        y_position = height - 220
        total_amount = 0
        for item, quantity, price in items:
            c.drawString(50, y_position, item)
            c.drawString(300, y_position, str(quantity))
            c.drawString(400, y_position, f"${price:.2f}")
            total = quantity * price
            c.drawString(500, y_position, f"${total:.2f}")
            y_position -= 20
            total_amount += total

        # Total amount
        c.setFont("Helvetica-Bold", 12)
        c.drawString(400, y_position - 20, "Total Amount:")
        c.drawString(500, y_position - 20, f"${total_amount:.2f}")

        # Save the PDF
        c.save()

@app.route('/')
def index():
    return render_template_string('''
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Invoice Maker</title>
    </head>
    <body>
        <h1>Invoice Maker</h1>
        <form action="/generate_invoice" method="post">
            <h2>Shop Details</h2>
            <label for="shop_name">Shop Name:</label>
            <input type="text" id="shop_name" name="shop_name" required><br>
            <label for="shop_address">Shop Address:</label>
            <input type="text" id="shop_address" name="shop_address" required><br>
            <label for="shop_phone">Shop Phone:</label>
            <input type="text" id="shop_phone" name="shop_phone" required><br>

            <h2>Customer Details</h2>
            <label for="customer_name">Customer Name:</label>
            <input type="text" id="customer_name" name="customer_name" required><br>
            <label for="customer_address">Customer Address:</label>
            <input type="text" id="customer_address" name="customer_address" required><br>

            <h2>Items</h2>
            <label for="item1">Item 1:</label>
            <input type="text" id="item1" name="item1" required>
            <label for="quantity1">Quantity:</label>
            <input type="number" id="quantity1" name="quantity1" required>
            <label for="price1">Price:</label>
            <input type="number" step="0.01" id="price1" name="price1" required><br>

            <label for="item2">Item 2:</label>
            <input type="text" id="item2" name="item2">
            <label for="quantity2">Quantity:</label>
            <input type="number" id="quantity2" name="quantity2">
            <label for="price2">Price:</label>
            <input type="number" step="0.01" id="price2" name="price2"><br>

            <label for="item3">Item 3:</label>
            <input type="text" id="item3" name="item3">
            <label for="quantity3">Quantity:</label>
            <input type="number" id="quantity3" name="quantity3">
            <label for="price3">Price:</label>
            <input type="number" step="0.01" id="price3" name="price3"><br>

            <h2>Invoice Details</h2>
            <label for="invoice_number">Invoice Number:</label>
            <input type="text" id="invoice_number" name="invoice_number" required><br>

            <button type="submit">Generate Invoice</button>
        </form>
    </body>
    </html>
    ''')

@app.route('/generate_invoice', methods=['POST'])
def generate_invoice():
    shop_name = request.form['shop_name']
    shop_address = request.form['shop_address']
    shop_phone = request.form['shop_phone']
    customer_name = request.form['customer_name']
    customer_address = request.form['customer_address']
    items = [
        (request.form['item1'], int(request.form['quantity1']), float(request.form['price1'])),
        (request.form['item2'], int(request.form['quantity2']), float(request.form['price2'])),
        (request.form['item3'], int(request.form['quantity3']), float(request.form['price3']))
    ]
    invoice_number = request.form['invoice_number']
    output_filename = f"invoice_{invoice_number}.pdf"

    invoice_maker = InvoiceMaker(shop_name, shop_address, shop_phone)
    invoice_maker.create_invoice(customer_name, customer_address, items, invoice_number, output_filename)

    return send_file(output_filename, as_attachment=True)

if __name__ == '__main__':
    app.run(debug=True)
