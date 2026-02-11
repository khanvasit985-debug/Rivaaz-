export default function ProductCard({ product }) {
  const [quantity, setQuantity] = useState(0);

  const handleAddToCart = () => {
    setQuantity(prev => prev + 1);
    console.log(`${product.name} added to cart!`);
  };

  return (
    <Card className="w-64 p-4 shadow-lg">
      <CardContent className="flex flex-col items-center gap-4">
        <div className="aspect-square bg-gray-100 w-full rounded-md flex items-center justify-center">
          {/* Product Image Placeholder */}
          <span className="text-gray-400">Image</span>
        </div>
        
        <div className="text-center">
          <h3 className="font-bold text-lg">{product?.name || "Cool Product"}</h3>
          <p className="text-sm text-gray-500">${product?.price || "19.99"}</p>
        </div>

        <Button 
          onClick={handleAddToCart} 
          className="w-full flex gap-2 items-center"
        >
          <ShoppingCart size={16} />
          {quantity > 0 ? `In Cart (${quantity})` : "Add to Cart"}
        </Button>
      </CardContent>
    </Card>
  );
}
