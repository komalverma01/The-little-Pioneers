# Pre-Order Tagging Setup Guide

## What Has Been Implemented

When a customer adds a pre-order item to their cart, a hidden line item property `_pre_order` with value `true` is automatically added. This property will be included in the order when the customer checks out.

## Setting Up Shopify Flow to Tag Orders

To automatically add the "pre_order" tag to orders containing pre-order items, follow these steps:

### Step 1: Access Shopify Flow
1. Go to your Shopify Admin
2. Navigate to **Settings** > **Apps and sales channels**
3. Click on **Shopify Flow** (if you don't have it, you may need to install it or upgrade your plan)

### Step 2: Create a New Workflow
1. Click **Create workflow**
2. Name it: "Tag Pre-Order Orders"

### Step 3: Set Up the Trigger
1. Select **Order created** as the trigger
2. This will run whenever a new order is placed

### Step 4: Add Condition (Optional but Recommended)
1. Click **Add condition**
2. Select **Line item property**
3. Choose: **Line item property** equals `_pre_order`
4. Set value to: `true`
5. This ensures only orders with pre-order items get tagged

### Step 5: Add Action
1. Click **Add action**
2. Select **Add order tags**
3. Enter the tag: `pre_order`
4. Click **Save**

### Step 6: Activate the Workflow
1. Toggle the workflow to **Active**
2. Click **Save**

## How It Works

1. When a customer adds a pre-order item (inventory = 0) to cart, the property `_pre_order: true` is added
2. When the order is placed, Shopify Flow detects this property
3. The workflow automatically adds the "pre_order" tag to the order
4. You can now easily filter and identify pre-orders in your order list

## Viewing Pre-Order Orders

In your Shopify Admin:
- Go to **Orders**
- Use the filter/search to find orders with tag: `pre_order`
- All pre-orders will be clearly identified

## Alternative: Manual Tagging

If you don't have Shopify Flow, you can:
1. Check order line items for the `_pre_order` property
2. Manually add the "pre_order" tag to those orders
3. Or use a third-party app that can tag orders based on line item properties
