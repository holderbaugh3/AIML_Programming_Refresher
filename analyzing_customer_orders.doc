# -*- coding: utf-8 -*-
"""
Created on Wed Jul 17 11:02:08 2025

@author: Jana Holderbaugh

Course-End Project: Analyzing Customer Orders Using Python

Overview
In this project, you will analyze customer orders using Python data structures to classify
products, identify customer purchasing patterns, and generate business insights. This
analysis will help you understand which products are most popular, which customers
are high-value, and how purchase behavior varies across different categories. You will
leverage lists, tuples, dictionaries, and sets, along with loops and conditionals, to
process and organize customer order data efficiently.

"""

class OrderAnalysis:
    customerNames = []
    #list of tuples (customer name, product, price, category)
    orders = []
    customerOrders = dict()
    
    def storeOrder(self, name, product, price, category):
        self.orders.append((name, product, price, category))
        if name in self.customerNames:
            self.customerNames.append((name, product, price, category))
            self.customerOrders[name].append((product, price, category))
        else:
            self.customerOrders[name] = [(product, price, category)]
            self.customerNames.append(name)

    def categorizeProducts(self):
        categories = set()
        productCategories = dict()
        for order in self.orders:
            categories.add(order[3])
            productCategories[order[0]] = order[3]
           
        print("Categories in Database: " + str(categories)[1:-1] + ".\n")
    
    def analyzeCustomerOrders(self):
        customerTotals = dict()
        for customer in self.customerOrders:
            customerOrders = self.customerOrders[customer]
            customerTotal = 0
            for order in customerOrders:
                customerTotal += order[1]
        
            customerCategory = "low-value buyer"
            if customerTotal > 100:
                customerCategory = "high-value buyer"
            elif customerTotal > 50 and customerTotal <= 100:
                customerCategory = "moderate buyer"
            customerTotals[customer] = (customerTotal, customerCategory)
        return customerTotals
    
    
    def businessInsights(self):
        categoryTotals = dict()
        products = set()
        for order in self.orders:
            products.add(order[1])
            if order[3] in categoryTotals.keys():
                categoryTotals[order[3]] += order[2]
            else:
                categoryTotals[order[3]] = order[2]
        for category in categoryTotals:
            print("{} total spent on the category of ${}.\n".format(category, categoryTotals[category]))
            
        print("Unique products: " + str(products)[1:-1] + ".\n")
                
        boughtElectronics = set([o[0] for o in self.orders if o[3] == "Electronics"])
        
        def sorting_helper(self, customer):
            value = self.analyzeCustomerOrders()[customer]
            return value[0]
        
        sortedCustomers = sorted(self.analyzeCustomerOrders(), key=lambda customer: sorting_helper(self, customer))
        print("Bought Electronics: " + str(boughtElectronics)[1:-1] + ".\n")
        print("Highest Spenders: " + sortedCustomers[-1] + ", " + sortedCustomers[-2] + ", " + sortedCustomers[-3] + ".\n")
        
    def display(self):
        print("Customer Spending and Customer:")
        customerTotals = self.analyzeCustomerOrders()
        for customer in customerTotals:
            customerTotal = customerTotals[customer]
            print("{} spent a total of ${} making them a {}.".format(customer, customerTotal[0], customerTotal[1]))
        print()
            
        categories = dict()
        #make dictionary of categories and who bought them
        for order in self.orders:
            if order[3] in categories.keys():
                categories[order[3]].add(order[0])
            else:
                categories[order[3]] = set([order[0]])
        multiSpender = set()
        cats = list(categories)
        for l in range(len(cats)):
            leftKey = cats[l]
            for r in range(l+1, len(cats)):
                rightKey = cats[r]
                multiSpender |= categories[leftKey].intersection(categories[rightKey])
                
        print("Category Insights: ")
        self.categorizeProducts()
        print("Customers Who Bought From Multiple Categories: " + str(multiSpender)[1:-1] + ".\n")
        
        elcAndClo = categories['Electronics'].intersection(categories['Clothing'])
        print("Customers Who Bought Electronics and Clothing: " + str(elcAndClo)[1:-1] + ".\n")
        
        print("Business Insights: ")
        self.businessInsights()
        
        
        
                
                
        
    
oa = OrderAnalysis()
oa.storeOrder("Bruce Wayne", "Batcomputer", 50000, "Electronics")
oa.storeOrder("Luke Skywalker", "Lightsaber", 0, "Electronics")
oa.storeOrder("Leia Organa", "Empress Dresses", 25000, "Clothing")
oa.storeOrder("Leia Organa", "Disguise", 500, "Clothing")
oa.storeOrder("Jason Vorhees", "Knife", 20, "Weapons")
oa.storeOrder("Han Solo", "Milenium Falcon", 10000000, "Electronics")
oa.storeOrder("Han Solo", "Snazzy Vest", 10, "Clothing")
oa.storeOrder("Lando Calrissian", "Silly lil Cape", 200, "Clothing")
oa.storeOrder("Darth Vader", "Arm", 10000, "Prosthetics")
oa.storeOrder("Darth Vader", "Leg", 15000, "Prosthetics")
oa.storeOrder("Darth Vader", "Leg", 15000, "Prosthetics")
oa.storeOrder("Darth Vader", "Death Star", 5000000000, "Electronics")
oa.storeOrder("Chwebacca", "Crossbow", 90, "Weapons")
oa.storeOrder("Darth Vader", "Lightsaber", 0, "Electronics")
oa.display()

    