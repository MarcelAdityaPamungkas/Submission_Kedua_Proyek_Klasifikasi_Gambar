# Konversi Model ke Dalam Format SavedModel
`export_dir = "saved_model/"`\
`tf.saved_model.save(model, export_dir)`

# Convert model menjadi model.tflite
`converter = tf.lite.TFLiteConverter.from_keras_model(model)`\
`tflite_model = converter.convert()`
 
`tflite_model_file = pathlib.Path("model.tflite")`\
`tflite_model_file.write_bytes(tflite_model)`

# Konversi model.h5 ke tfjs_model
`model.save("model.h5")`\
`!tensorflowjs_converter --input_format keras \`\
    `--weight_shard_size_bytes 4294967296 \`\
    `model.h5 tfjs_model`
